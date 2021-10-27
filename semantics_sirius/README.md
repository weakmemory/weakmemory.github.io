To work through Coq exercises for semantics course, you need to prepare an environment. 

The best experience is achieved with direct installation into your system.
An easier way is to use a virtual machine. 

Please prepare a working environment before the practice session starts. Don't hesitate to contact teachers in case of problems. 

# Manual installation

You can prepare the environment by hand. Any system capable of running `opam` should fit (we tested the process on Linux only though). Note that it may require system-specific steps not covered here.

1. [Install ``opam``](https://opam.ocaml.org/doc/Install.html) if you don't have one (we tested the process with version ``2.1.0``). 
2. Perform ``opam`` initialization: ``opam init -a``. The ``-a`` key makes adjustments in your ``~/.profile`` to ease the ``opam`` usage, so we recommend keeping it. 
3. Create a separate ``opam`` environment, switch to it and update the current shell: ``opam switch create semantics 4.12.0; opam switch set semantics; eval $(opam env)``. Note that creating an environment may take some time. 
4. Install project dependencies. First, make sure that you're using the correct ``opam`` environment: ``opam switch`` should highlight the newly created ``semantics`` environment and shouldn't output a warning. If not (it may happen if you've opened another terminal window), execute ``opam switch semantics; eval $(opam env)``. Now, navigate to the cloned Git repo and run ``configure`` there. It will add an additional repository to the current ``opam`` environment and install the required dependencies. Note that it may take about 20 minutes. The exact versions of dependencies are specified in ``configure`` file but their latest versions should work as well. 
5. Now the environment should be ready. Make sure that ``make -j 4`` command  successfully goes through ``*.v`` files without errors. 
6. To edit proofs you can use any appropriate editor available on your system. Make sure that you can execute proofs in an interactive mode in that editor. 
   - If you choose Emacs note that some characters are missing in the default Emacs font. On Debian-based distributives it can be fixed by installing the ``ttf-ancient-fonts`` package; on other distributives, there should be similar packages. Otherwise, Proof General with ``company-coq`` installed should display everything fine. 

# Using the virtual machine

The easiest way to access the environment is to use the pre-built virtual machine.

1. Install VirtualBox (we tested the process with version 6.1) with Oracle VM VirtualBox Extension pack.
2. Open VirtualBox and navigate to ``File/Import Appliance``. Provide the path to the ``coq-env.ova`` file and follow wizard instructions to create a VM.
3. Run the newly created VM. 
	- If a "RawFile#0 failed to create the raw output file ..." error occurs, try disabling serial ports in VirtualBox (`right click on VM -> Settings -> Serial Ports -> uncheck "Enable Serial Port" boxes`). See [the discussion](https://github.com/joelhandwell/ubuntu_vagrant_boxes/issues/1) of the related problem.
4. Login with username and password "vagrant".
5. Navigate to ``/home/vagrant/semantics`` in a terminal and run ``make -j 4``. Make sure that the command successfully goes through ``*.v`` files without errors.
6. The VM includes the following proof editors:
   - Emacs w/ Proof General;
   - Vim w/ Coqtail;
   - VSCode w/ VSCoq.

