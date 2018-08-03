# Align your project and domain

We consider that your Domain model should always be reflected in your code. This translates, in part, in the way that you organize your project.
In Domain Driven Design it is strongly advised to deploy your modules according to domain elements, not depending on technical layers. It helps in terms of scalability, maintainablity, but also in understanding your project. There is only so much the human brain can make up for and it is difficult to understand what you are working on if your domain element is separated accross modules. You should follow this rule when organizing your project.

## Example

Features should be independent from each others. 
Adding more features should not impact other features. Each feature should be 
stored into a related domain folder. This pattern is described as micro features.

**Prefered:**

```
MyTune
    -- User
        -- Authenticate
            -- User Interface
            -- Business Logic
    -- Playlist
        -- List
            -- User Interface
            -- Business Logic
        -- Read
            -- User Interface
            -- Business Logic
    -- Tracks
        -- List
            -- User Interface
            -- Business Logic
```

**Not Prefered:**

```
MyTune
    -- ViewControllers
        -- UserAuthenticationViewControllers.swift
        -- UserPlaylistViewControllers.swift
        -- PlaylistInformationViewControllers.swift
        -- PlaylistTracksViewControllers.swift
    -- ViewModels
        -- UserAuthenticationViewModels.swift
        -- UserPlaylistViewModels.swift
        -- PlaylistInformationViewModels.swift
        -- PlaylistTracksViewModels.swift
```

It will help developers to quickly identify a specific feature and  define 
feature boundaries. Those features can also be delivered as separate modules.