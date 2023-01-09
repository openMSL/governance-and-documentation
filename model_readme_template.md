# Model Name

< Github Action Badges of CI Pipeline >

Enter a short description of the model. What is the purpose of the model? What is the general modeling approach? What inputs does the model need and what outputs does it generate?<br><br>

< Eye-catcher Image >

## Modeling Approach
Put details about the inner workings of the model here. Describe the modeling approach in detail. What is the structure of the model? What modules is it comprised of? What sensor effects are represented in the model and how are they modeled?


## Parameterization
What parameters are used internally? Which parameters can be set by the user?
Each parameter should have a short description as shown in the following example.

| Parameter                      | Description                                                         |
| ------------------------------ | ------------------------------------------------------------------- |
| no_of_beams_vertical           | Number of beams in vertical direction, e.g. layers, of the lidar    |
| no_of_beams_horizontal         | Number of beams per layer of the lidar                              |

## Interface
What interfaces are used as model input and model output? All required field of the interface shall be named in a list as shown in the following example.

### Input: Required Fields in OSI3::SensorView
- sensor_view.mounting_position
- sensor_view.global_ground_truth.timestamp
- sensor_view.global_ground_truth.host_vehicle_id
- sensor_view.global_ground_truth.stationary_object.id
- sensor_view.global_ground_truth.stationary_object.base.position
- sensor_view.global_ground_truth.stationary_object.base.orientation
- sensor_view.global_ground_truth.stationary_object.base.dimension

### Output: Fields in OSI3::SensorData Filled by the Sensor Model
- sensor_data.timestamp
- sensor_data.moving_object_header.measurement_time
- sensor_data.moving_object_header.cycle_counter
- sensor_data.moving_object_header.data_qualifier
- sensor_data.moving_object.header.ground_truth_id
- sensor_data.moving_object.header.tracking_id
- sensor_data.moving_object.header.age
- sensor_data.moving_object.base.position
- sensor_data.moving_object.base.orientation
- sensor_data.moving_object.base.orientation_rate
- sensor_data.moving_object.base.velocity
- sensor_data.moving_object.base.acceleration
- sensor_data.moving_object.base.dimension


## Build Instructions
What are the dependencies for building the model?

Give step by step build instructions for supported operating systems. The following is an example for building a model as an FMU in Ubuntu.

### Build Model in Ubuntu 18.04 / 20.04

1. Clone this repository <ins>with submodules</ins>:
    ```bash
    $ git clone https://github.com/openMSL/your-model.git --recurse-submodules
    ```
2. Build the model by executing in the extracted project root directory:
    ```bash
    $ mkdir cmake-build
    $ cd cmake-build
    # If FMU_INSTALL_DIR is not set, CMAKE_BINARY_DIR is used
    $ cmake -DCMAKE_BUILD_TYPE=Release -DFMU_INSTALL_DIR:PATH=/tmp ..
    $ make
    ```
3. Take FMU from `FMU_INSTALL_DIR`


## Credits
Give credits to funding or third-party contributions. If the model is further described in a publication, it can also be named here.
