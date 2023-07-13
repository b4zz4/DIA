# Diffusion Image Analogies
<div>
<a src ="https://cmp.felk.cvut.cz/~subrtade/">Adéla Šubrtová</a>,
<a src ="https://research.adobe.com/person/michal-lukac/">Michal Lukáč</a>,  
<a src ="https://cmp.felk.cvut.cz/~cechj/">Jan Čech</a>,  
David Futschik,  
<a src ="https://research.adobe.com/person/eli-shechtman/">Eli Shechtman</a>,  
<a src ="https://dcgi.fel.cvut.cz/home/sykorad/">Daniel Sýkora</a>,  
</div>

![DIA_Teaser](https://github.com/subrtadel/DIA/assets/129282989/5f11b34d-9f49-47a2-b90d-60ee36ebc3bc)
This is the official repository for the Diffusion Image Analogies paper published at the SIGGRAPH 2023 Conference Proceedings.

***

## Installation

1. Clone the repo
   ```sh
   git clone --recurse-submodules https://github.com/subrtadel/DIA.git
   ```
2. Create environment 
    ```
    conda install python=3.8.5 pip=20.3 cudatoolkit=11.3 pytorch=1.11.0 torchvision=0.12.0 numpy=1.19.2 -c pytorch -c conda-forge -c defaults
    ```
3. Install packages
   ```sh
   pip install -r requirements.txt
   cd ./DIA/stable-diffusion/
   pip install -e git+https://github.com/CompVis/taming-transformers.git@master#egg=taming-transformers
   pip install -e .
   ```
4. Download the [sd-v1-4.ckpt model](https://huggingface.co/CompVis/stable-diffusion-v-1-4-original) and put it into correct folder
    ```
    mkdir -p ./DIA/stable-diffusion/models/ldm/stable-diffusion-v1/

    ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

***


## Usage

1. Upload images into `./dataset/raw_data/` folder.

2. Run `process_new_data.py`. The images are assigned `file_id`s in a `%05d` format.

3. Define the triplets in a `.csv` file. Refer to the images by their `file_id`. 
    Example file is `triplets.csv`. Either with of without filename suffixes is fine.

4. Run the `precompute_noises_and_conditionings.py` script. This may take a while.
5. Check the `./config/analogy_params.yaml`.
6. Run the `do_analogies.py` script.



***

## BibTeX

    @inproceedings{Subrtova2023DIA,
        title = {Diffusion Image Analogies},
        author = {A. \v{S}ubrtov\'{a} and M. Luk\'{a}\v{c} and J. \v{C}ech and D. Futschik and E. Shechtman  and D. S\'{y}kora},
        booktitle = {ACM SIGGRAPH 2023 Conference Proceedings},
        year = {2023}
      }