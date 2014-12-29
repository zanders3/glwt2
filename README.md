glwt2
=====

GLWT v2.0 now in a single file and easier to use. It opens a nice OSX window and creates an OpenGL 3.2+ context.

To use simply create a new XCode project and add glwt.mm and glwt.h to the project. This main.c will get you started:

    #include "glwt.h"
    
    void draw(float time)
    {
        glClearColor(1.0f, 0.0f, 0.0f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);
    }
    
    int main(int argc, char *argv[])
    {
        return initglwt("Hello, world!", 800, 600, false);
    }
