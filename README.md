# Vector Battle

- Anthony Leotta
- 6/25/2019

## Libraries

The following libraries will be required.

- sdl
- glew
- glfw
- glm

## Setup SDL

- create a folder called libs

- [Download SDL](https://www.libsdl.org/download-2.0.php)

- download SDL2-devel-2.0.9-VC.zip (Visual C++ 32/64-bit)


## Create a C++ Project

- Start Visual Studio 2017

- Create new Empty Project

- Add New Item main.cpp

- Click on Properties

    - C/C++ General

        - Additional Include Directories

            - add SDL include path

    - Linker General

        - Additional Library Directories

            - add SDL lib path for x64

        - to Linker/Input Additional Dependencies add

            - SDL2.lib

            - SDL2main.lib

    - change Linker/System SubSystem to Console (/SUBSYSTEM:CONSOLE)

    - copy SDL2.dll to came folder as main.cpp

- Add this code to main.cpp

```
#include "SDL.h"

int main(int argc, char *argv[]) {

	SDL_Init(SDL_INIT_EVERYTHING);

	SDL_Window *window = SDL_CreateWindow("Hello, World",	SDL_WINDOWPOS_CENTERED, SDL_WINDOWPOS_CENTERED, 600, 400, SDL_WINDOW_SHOWN);
	SDL_Renderer *renderer = SDL_CreateRenderer(window, -1, 0);

	SDL_SetRenderDrawColor(renderer, 0, 255, 0, 255);

	SDL_RenderClear(renderer);

	SDL_RenderPresent(renderer);

	SDL_Delay(3000);

	return 0;
}
```

