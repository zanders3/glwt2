glwt2
=====

GLWT v2.0 now in a single file and easier to use. It opens a nice OSX/Win32 window and creates an OpenGL 3.2+ context. This main.c will get you started:

    #include "glwt.h"
    
    void glwt_setup()
    {
    }
    
    void glwt_draw(float time)
    {
        glClearColor(1.0f, 1.0f, 1.0f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);
    }
    
    #ifdef _WIN32
    int CALLBACK WinMain(_In_  HINSTANCE hInstance, _In_  HINSTANCE hPrevInstance, _In_  LPSTR lpCmdLine, _In_  int nCmdShow)
    #else
    int main(int argc, char *argv[])
    #endif
    {
        return glwt_init("Hello, GLWT!", 800, 600, false);
    }

Compiling
---------

Simply create a new empty XCode/Visual Studio project and add glwt.(cpp/mm) and glwt.h to the project.

On Mac you will need to go to the 'Build Phases' XCode project settings tab and add the Cocoa.framework and OpenGL.framework for the project to link. Also ensure the glwt.mm file is an mm file *not* a cpp file.

Input
-----
Pressed keys are stored in the global ```bool glwt_keydown[255];``` structure as ascii keycodes. e.g. ```glwt_keydown['a']```. This will work for a-z and 0-9 keys. There are additional keys defined in the Keys enum at the top of the header file. This currently only works on windows - I'll be adding Mac support later!

