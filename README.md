Note: this code starts directly from Dr.Nathan Sprague's implementation of DQN. His codebase at https://github.com/spragunr/deep_q_rl.

Required packages
1. Cython
-http://cython.org/#download

2. Theano
-if later you get an error "cannot import host_from_gpu" you may need to update theano, see http://deeplearning.net/software/theano/install_ubuntu.html.

3. Pylearn2
-http://deeplearning.net/software/pylearn2/

4. ALE (with replaced controller file)
-Download ALE at http://www.arcadelearningenvironment.org/downloads/
-unzip
-copy file in ale_files to replace ale_0.4.4/ale_0_4/src/controllers/rlglue_controller.cpp
-cd ale_0.4.4/ale_0_4
-cp makefile.unix makefile (use makefil.mac if you have mac)
-make

5. rl-glue core
-https://code.google.com/p/rl-glue-ext/wiki/RLGlueCore

6. rl-glue python codec
-https://code.google.com/p/rl-glue-ext/wiki/Python

Required changes:
1. cd src && vi ale_run.py
change ROM, ALE, GLUE paths to be your own locations
GLUE path should be like /u/[usrname]/lib/bin/rl_glue
ALE path should be like /[...]/ale_0.4.4/ale_0_4/ale
ROM path is wherever you put your rom files

To run the experiment:
python ale_run.py

Plot results:
python plot_results.py [data folder path]/results.csv

Watch performance:
python ale_run_watch.py [data folder path]/network_file_99.pkl
