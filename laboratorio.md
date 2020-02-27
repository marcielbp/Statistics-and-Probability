File:

````shell
aluno@dti:~$ conda info --envs
# conda environments:
#
# base                  *  /home/aluno/miniconda2
# ds                       /home/aluno/miniconda2/envs/ds
# probS                    /home/aluno/miniconda2/envs/probS
# escolher probS
aluno@dti:~$ source activate probS
(probS) aluno@dti:~$ conda info --envs
# conda environments:
#
base                     /home/aluno/miniconda2
ds                       /home/aluno/miniconda2/envs/ds
probS                 *  /home/aluno/miniconda2/envs/probS

(probS) aluno@dti:~$ jupyter-notebook
````
