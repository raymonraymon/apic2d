Affine Particle in Cell in 2D
================
![Screenshot](http://www.cs.columbia.edu/cg/raymond/apic2d.jpg)
APIC2D is an educational project to illustrate the affine-particle-in-cell algorithm in 2D, for water simulation.

The papers implemented here include:

Jiang, Chenfanfu, et al. "The affine particle-in-cell method." ACM Transactions on Graphics (TOG) 34.4 (2015): 51.

Batty, Christopher, Florence Bertails, and Robert Bridson. "A fast variational framework for accurate solid-fluid coupling." ACM Transactions on Graphics (TOG). Vol. 26. No. 3. ACM, 2007.

Ando, Ryoichi, Nils Thurey, and Reiji Tsuruno. "Preserving fluid sheets with adaptively sampled anisotropic particles." IEEE transactions on visualization and computer graphics 18.8 (2012): 1202-1214.

Brackbill, Jeremiah U., and Hans M. Ruppel. "FLIP: A method for adaptively zoned, particle-in-cell calculations of fluid flows in two dimensions." Journal of Computational physics 65.2 (1986): 314-343.

Fei, Yun (Raymond), et al. "Revisiting Integration in the Material Point Method: A Scheme for Easier Separation and Less Dissipation." ACM Transactions on Graphics (TOG) 40.4 (2021): 109.

It contains multiple integrators that you may switch and compare through changing the `integration_scheme` variable in the code. Its value can be one of the following:
```
IT_PIC: original particle-in-cell (PIC)
IT_FLIP: original fluid-implicit-particle (FLIP)
IT_RPIC: rotational particle-in-cell (RPIC)
IT_APIC: affine particle-in-cell (APIC)
IT_AFLIP: affine fluid-implicit-particle (AFLIP)
IT_ASFLIP: affine separable fluid-implicit-particle (ASFLIP)
```

It also supports using different orders for velocity evaluation, where one may change the `velocity_order` variable in the code. Its value can be one of the following:
```
VO_EULER: first order evaluation
VO_RA2: Ralston's second order evaluation
VO_RK3: Runge Kutta's 3rd-order method
VO_RK4: Runge Kutta's 4rd-order method
```

Dependencies
--------------------
APIC2D depends on the Eigen libraries (included) as well as GLUT for simple visualization.

Compilation
-----------------
To compile APIC2D, you'll need CMake on Mac OS X or Linux, or CMake-GUI (https://cmake.org) on Windows.

On Mac OS X or Linux:
1. make a directory, say, *build*, with *mkdir build*, enter the *build* directory, type *cmake ..*
2. Optionally you can adjust the options with *ccmake .*
3. type *make* to compile the code. For speeding up the compilation process you may use *make -j*.

On Windows:
1. open CMake-GUI, enter the correct directory for source code and build. Then click *Configure*, choose your installed version of the Microsoft Visual Studio.
2. after configuration you may find several libraries not found, check the *Advanced* box and locate those missing libraries manually. Please make sure you have picked the libraries corresponding to the architecture you have selected (say, 32-bit libraries for x86, and 64-bit libraries for x64).
3. click generate after fixing all missing variables to generate your Visual Studio solution.
4. open the solution and compile the code.

编译过程
需要freeglut x86版本支持，所以先用vs2019 x86编译了freeglut，然后相应加入头文件和库文件，运行dll
