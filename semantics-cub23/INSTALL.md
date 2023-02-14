### [To the course page](index)

You need to set up an environment on your computer to solve Coq tasks.
We recommend two alternatives:
- Direct installation on your machine with Linux/MacOS (harder to setup, but much more convenient to use);
- Usage of a provided virtual machine image (easier to setup, but less convenient to use).

Once you finish setting up Coq and necessary libraries, you will also need to setup an editor to be able to use Coq interactively.
Check the corresponding section below.

# Direct installation on your machine with Linux/MacOS

1. In order to install Coq we will use [``opam`` package manager](https://opam.ocaml.org/).
   You can find the installation instructions for ``opam`` [here](https://opam.ocaml.org/doc/Install.html).
   Please note, that as of today ``opam`` **does not support** Windows.

2. Initialize ``opam`` by running the following command.

    ```sh
    opam init -a
    ```

3. Create a new [switch](https://opam.ocaml.org/doc/Manual.html#Switches). 
   Switches allow you to easily change the version of OCaml compiler toolchain used to build Coq. 
   Switch creation process may take few minutes.

    ```sh
    opam switch create semantics 4.12.0
    opam switch set semantics
    eval $(opam env)
    ```

4. Install Coq. In this course we will use Coq version 8.15.2. 
   You can tell ``opam`` to fix this version using `opam pin` command 
   (it means that ``opam`` will not try to install more recent versions, even if they are available).
   Coq installation may take few minutes. 
   

    ```sh
    opam remote add coq-released https://coq.inria.fr/opam/released
    opam pin add coq 8.15.2
    opam install coq
    ```

5. Install additional Coq libraries required by this course.

   ```sh
   opam remote add coq-weakmemory-local -k git https://github.com/weakmemory/local-coq-opam-archive
   opam install coq-hahn
   ```

6. Check that your environent is propery set up. 
   Download the course assignments repository. 
   In the root folder of course assignments run the ``make`` command. 
   It should start proof-checking the file ``src/b1.v`` and then fail with the message ``Tactic failure: tauto failed``. 

   
7. For proof editing you may use any of the editors proposed in the corresponding section of this manual below.
   Make sure you have correctly set up editor of your choice.
   Try to open file ``src/b1.v`` and proof-check it in the step-by-step mode (see below). 
   It should be checked successfully up until lemma ``nat_eq_tests_pass``. The latter should fail with the message mentioned above.

# Usage of a provided virtual machine image

You can use the [provided virtual machine](https://drive.google.com/file/d/1mn-CwnQKMyEUSTNnCKTPT82Wf7Z-bpin/view?usp=share_link) with Ubuntu 22.04 OS.
It already has Coq, required libraries and all the code editors installed.

1. Install [VirtualBox](https://www.virtualbox.org/) (we recommend version 6.1), 
   and [Oracle VM VirtualBox Extension pack](https://www.virtualbox.org/wiki/Downloads).

2. Import the downloaded `.ova` file following the 
   [instructions](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/ovf.html#ovf-import-appliance) 
   in the official documentation.

3. Run the imported VM. 
  - In case of the error "RawFile#0 failed to create the raw output file ..." try to disable serial ports
    (In Virtual Box UI select the VM -> Settings -> Serial Ports -> uncheck "Enable Serial Port").

4. Log in to the OS. 
  - username: `vagrant`
  - password: `vagrant`

5. Check that VM is propery set up.
   Download the course assignments repository. 
   In the root folder of course assignments run the `make` command. 
   It should start proof-checking file `src/b1.v` and then fail with the message `Tactic failure: tauto failed`. 

# Editors for interactive work on Coq proofs

Proofs in Coq are intended to be written interactively. To help with that, there exist IDEs and plugins listed below.
To check that you setted up an editor from the list correctly, open a `*.v` file from the repo
and execute command "make a step" in the editor.

- (**RECOMMENDED OPTION**) [CoqIDE](https://coq.inria.fr/refman/practical-tools/coqide.html), a specialized editor for Coq. <br/>
  * Depending on your system, it may require you to install few packages. 
  For example, on Ubuntu, you need to install ``pkg-config``, ``libgtk-3-dev``, and ``libgtksourceview-3.0-dev``. 
  CoqIDE itself can be installed via ``opam``: ``opam install coqide``.
  * **Make a step** command: button `->` in the toolbox.

- [VSCode](https://code.visualstudio.com/) + [VSCoq](https://github.com/coq-community/vscoq). 
  * **Make a step** command: a key combination ``Alt-Down`` (on Linux) and `Ctrl-Option-Down` (on MacOS).
  * Note that, in VSCode, you need to open the root folder of a Coq project you are working on, not just a file from it.
    Otherwise, for a multi-file project, you may have a problem with importing local files from the project.

- [Emacs](https://www.gnu.org/software/emacs/) + [Proof General](https://proofgeneral.github.io/). 
  * **Make a step** command: button "> Next" in the toolbox, or `C-c C-n` key combination by default.
  * Find other hot keys [here](https://proofgeneral.github.io/doc/master/userman/Basic-Script-Management/#Basic-Script-Management) (section §2.6).
  * In Emacs editor some symbols used in the proofs are absent in the default font. 
    In the Debian-based distribution this issue can be fixed by installing the package ``ttf-ancient-fonts``.

- [Vim](https://www.vim.org/) + [Coqtail](https://github.com/whonore/Coqtail). 
  * **Make a step** command: a sequence ``<leader> c j`` (``<leader>`` equals to ``\`` by default).
