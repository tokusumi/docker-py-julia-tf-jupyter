FROM julia:1.3.0 as julia
FROM tensorflow/tensorflow:2.0.0-py3-jupyter

# copy Julia build file and set path for julia
COPY --from=julia /usr/local/julia /usr/local/julia
ENV PATH=/usr/local/julia/bin:$PATH

# install package to use Julia in Jupyter Notebook
RUN julia -e 'using Pkg; Pkg.add("IJulia"); using IJulia'

# install packages to call Julia function in Python
RUN python -m pip install pip --upgrade
RUN python -m pip install julia \
    && python -c 'import julia; julia.install()'


WORKDIR /notebooks
ADD requirements.txt /notebooks/requirements.txt

RUN python -m pip install -r requirements.txt
COPY . /notebooks


CMD jupyter notebook --ip=0.0.0.0 --allow-root