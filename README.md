glwt2
=====

GLWT v2.0 now in a single file and easier to use. It opens a nice OSX/Win32 window and creates an OpenGL 3.2+ context. This main.c will get you started:

    #include "glwt.h"
    
    void draw(float time)
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
        return initglwt("Hello, GLWT!", 800, 600, false);
    }

Compiling
---------

Simply create a new empty XCode/Visual Studio project and add glwt.(cpp/mm) and glwt.h to the project.
