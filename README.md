# Chez-Compiler Project

## Project Overview
This project is a **Chez-Compiler** that compiles a large subset of Scheme into Intel x86, 64-bit assembly language. The generated assembly code is then assembled into a standalone executable using the Newtide Assembler (nasm). The project was developed as part of the **Compilation course at Ben-Gurion University (2022/2023, Semester 1)**. A custom tester was created to assist in verifying the functionality of the compiler.

## Assumptions
- The project is designed to run on **GNU/Linux** (this has not been tested on Windows).
- The `Code_Generator` module should be located in `code-gen.ml`. If your file structure differs, you will need to edit `tester.ml` at line 1 to adjust the `#use` directive accordingly.

## How to Run the Tester
1. **Download all the files:**
   - Place the tester files and your project files (like `code-gen.ml`) in the same directory.

2. **Add your project files:**
   - Ensure that `code-gen.ml` and any additional required files are in the same directory.

3. **Run the tester:**
   - Launch the tester using the following command:
     ```bash
     utop tester.ml
     ```

4. **Optional: Clean up output files:**
   - Use the following command to remove all generated output files:
     ```bash
     make clean
     ```

## Important Notes
- The tester generates an output file named `foo.asm` in the same working directory, which is constantly overwritten during testing. This file compiles into a standalone executable named `foo`.
- Tests are organized into segments based on different contexts. You can customize which contexts to run by editing `tester.ml`. Simply comment out the `run_cg_tests` lines for the contexts you do not wish to run.

## Project Structure
- **Code Generator:** The main module that handles the compilation from Scheme to assembly code (located in `code-gen.ml`).
- **Tester:** The custom tester (`tester.ml`) used to verify the correctness of the code generation.
- **Tests Hub:** Contains various test files organized by context within the `tests_hub` directory.
