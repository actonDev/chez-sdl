# Initialization and Shutdown

---
Procedure:
>(**SDL-INIT** *flags*) → boolean

Parameters:
>| *flags* : number        |
 | :---------------------- |
 | SDL-INIT-TIMER          |
 | SDL-INIT-AUDIO          |
 | SDL-INIT-VIDEO          |
 | SDL-INIT-JOYSTICK       |
 | SDL-INIT-HAPTIC         |
 | SDL-INIT-GAMECONTROLLER |
 | SDL-INIT-EVENTS         |
 | SDL-INIT-EVERYTHING     |

Returns:
>`#f` if there was a detectable error or `#t` otherwise.

C Function Name:
>`SDL_Init`

Examples:
```scheme
(sdl-init) ;Equivalent to (sdl-init SDL-INIT-VIDEO)
```
```scheme
(sdl-init
  SDL-INIT-EVERYTHING)
```
```scheme
(sdl-init SDL-INIT-VIDEO
          SDL-INIT-AUDIO)
```

Notes:
>Initializes the video subsystem by default.

---
Procedure:
>(**SDL-QUIT**) → void

C Function Name:
>`SDL_Quit`




# Configuration Variables

---
Procedure:
>(**SDL-CLEAR-HINTS!**) → void

C Function Name:
>`SDL_ClearHints`

---
Procedure:
>(**SDL-GET-HINT-BOOLEAN** *name* *default*) → boolean

Parameters:
>***name*** : A string. Name of the hint.

>***default*** : Return value if hint not found.

Returns:
>The setting of the hint or, ***default*** if the hint isn't applicable to the system.

C Function Name:
>`SDL_GetHintBoolean`

---
Procedure:
>(**SDL-SET-HINT!** *name* *value*) → boolean

Parameters:
>***name*** : A string. Name of the [hint.](data.md#hints)

>***value*** : A string. Value to set hint.

Returns:
>`#t` if hint was set or `#f` otherwise.

C Function Name:
>`SDL_SetHint`

---
Procedure:
>(**SDL-SET-HINT-W/-PRIORITY!** *name* *value* *priority*) → boolean

Parameters:
>***name*** : A string. Name of the [hint.](data.md#hints)

>***value*** : A string. Value to set hint.

>| *priority*        |
 | :---------------- |
 | SDL-HINT-DEFAULT  |
 | SDL-HINT-NORMAL   |
 | SDL-HINT-OVERRIDE |

Returns:
>`#t` if hint was set or `#f` otherwise.

C Function Name:
>`SDL_SetHintWithPriority`



# Error Handling

---
Procedure:
>(**SDL-CLEAR-ERROR!**) → void

C Function Name:
>`SDL_ClearError`

---
Procedure:
>(**SDL-GET-ERROR**) → string

Returns:
>A message describing an error that has occured.

C Function Name:
>`SDL_GetError`



# Querying SDL Version

---
Procedure:
>(**SDL-GET-VERSION**) → list

Returns:
>A list of 3 numbers. (major minor patch)

C Function Name:
>`SDL_GetVersion`

---
Procedure:
>(**SDL-GET-REVISION**) → string

Returns:
>A string identifying the version of SDL being used.

C Function Name:
>`SDL_GetRevision`

---
Procedure:
>(**SDL-GET-REVISION-NUM**) → number

Returns:
>A number identifying the version of SDL being used.

C Function Name:
>`SDL_GetRevisionNumber`