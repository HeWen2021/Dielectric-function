# Dielectric-function
How to use the code?
------------------------
This is my first time using github. So I guess this file is used to tell the public how to use my code. Right?
Lest's start.

1. Authority. 
The code "Diectric_function_QE.f90" using the formula in eps_man (manual of epsilon) of Quantum Espresso. The code "Diectric_function-Kresolved.f90" is a modified version. "Diectric_function-projection.f90" is based on the formula in paper 2> listed below. So if you use thesec codes, please cite 
1> QE: 10.1088/0953-8984/21/39/395502
2> My paper: 10.1002/adfm.202005977  (Light–Matter Interaction in Quantum Confined 2D Polar Metals, AFM)
3> My paper: https://doi.org/10.1002/adma.202104265 (Tunable 2D Group-III Metal Alloys, AM)
Thank you.

2. Pre-process
You need to install a patch of QE called "QE6.3_patch_eps_eigocc.patch".
The output: TDMATRIX.dat and Eig_Occ.dat. These are input of this code.

3. Why do we need this code?
Because you can easily adjust paramters includeing interband smearing and intraband smearing without run epsilon.x agin.
It saves much time because you don't need to compute dipole matrix agian and again.
In addition, you can use according code to compute the contriburions from transitions between specific atomic orbitals or k-resolved epsilon.
See 10.1002/adfm.202005977 (Light–Matter Interaction in Quantum Confined 2D Polar Metals, AFM)

4. Change the input.dat as you need.
There are three inputs. Please change the name to "input.dat" when running codes.
The first line is the directory you have TDMatrix.dat and Eig_Occ.dat.
Input.dat should be in the same directory as the code.

5. Convergence.
You should make sure your calculated epsilon is converged.
1> k-mesh. (I usually using doubled k-point in each direction.)
2> Bandnumbe. For imaginary part, it's dependent on what energy you are looking at. You should include all transitions you need when you choose a bandnumber. Our code provides a way to check convergence also. 

6. Input data of codes Diectric_function-projection.f90.
You need an additional file for this code. It is computed from projwfc.x of Quantum Espresso: "projwfc_up.dat".
You need to delete the head of this file untill "1  1". Please read mt code "Diectric_function-projection.f90" and have a try. 




