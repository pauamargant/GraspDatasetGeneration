# RobotGrasping

## File Structure

Please make sure to have the following file structure:

- `generate_data.py`
- `categories.txt`: Contains the IDs for the ShapeNet categories that will be sampled
- `resources`
    - `hsr`
        - `hsr_description`
        - `hsr_meshes`
    - `ssd3`
        - `datasets_bop`
            - `shapenetcorev2`
                - `models_bop-renderer_scale=0.1`: Contains the object files. They should be named `model_normalized_scaled.ply`
    - `cc_textures`
- `output`
- `dataset`

## Usage

- Use the config file to modify the paths if necessary. The important configuration options are:
    - `urdf_file`: Location of the `hsrb4s_fixed.urdf` file
    - `output_dir`: Location where the outputs (RGB, depth, and others) are stored
    - `dataset_output_path`: Location where the output images are stored
    - `shapenet_path`: Location of the `models_bop-renderer_scale=0.1` folder (the path includes the folder)
    - `textures_path`: Path to the `cc_textures`
    - `X_size`, `Y_size`: Resolution
- If necessary, use `requirements.txt` to install the requirements.
- Execute the file with the following command where $N$ is the total number of samples to generate:
    ```sh
    blenderproc run generate_data.py --render --num_sample N --positive_ratio .5
    ```