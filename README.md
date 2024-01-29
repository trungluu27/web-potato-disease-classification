# To start docker container
    docker run -it -v D:\WorkPlace\Potato_Disease:/Potato_Disease -p 8051:8051 --entrypoint /bin/bash tensorflow/serving

# To serve only latest model
    tensorflow_model_server --rest_api_port=8051 --model_name=potatoes_model --model_base_path=/Potato_Disease/models/

# To serve models using model config file
    tensorflow_model_server --rest_api_port=8051  --allow_version_labels_for_unavailable_models --model_config_file=/Potato_Disease/model.config

# To run and serve using model config file by only 1 line
    docker run -t --rm -p 8051:8051 -v D:\WorkPlace\Potato-Disease:/Potato-Disease tensorflow/serving --rest_api_port=8051 --model_config_file=/Potato-Disease/models.config