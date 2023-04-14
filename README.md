# avatar-repo

Team: Jared Scott, Yuxiang Ma, Young Jin Park, Malek Ibrahim

## Description

This repo houses all code related to controlling the HoloLens 2 for the Spring 2023 MIT 2.120 Robotics Class Project: An Avatar Rescue Bot. Specifically, we aim to achieve three key tasks:

1. Real-Time Navigation and Data Visualization
2. Force and Pump Override Adjustment Capability
3. Live Feed Display and Audio from Operator to Care Site

## Installation

Please see the instructions [here](https://docs.google.com/document/d/17jsBMaB0MUb40jxV13PPMbnD3ZUolpd2wvhG_WX-qII/edit) for a general overview of getting things working with the HoloLens 2.

You may also need some Python packages to run the scripts. It is recommended to create a new conda environment (download Miniconda [here](https://docs.conda.io/en/latest/miniconda.html)), activate it, and then install the requirments.txt file:

```
conda create -n 2.120 python=3.9
conda activate 2.120
pip install -r requirements.txt
```

## Usage

One simple test you can run is by navigating to the `Comms/Mock` folder and running the `mock_server.py` script on a server computer, and then running the `mock_hololens.py` script on a separate computer. Specifically, you may perform the following steps:

1. First obtain two laptops or computers to use, one to run the server code, and the other to run the mock client Python code.
2. On the client computer, edit the following line in `mock_hololens.py`:

```
# Replace the following with the IP address of the machine running the server
server_ip = "xx.xx.xx.xx"  # Define the server IP address (localhost in this case)
server_port = 21200  # Define the server port number
```

3. To find the server ip, open a terminal on the server computer and depending on your OS, run the following command:

```
# Windows
> ipconfig

# macOS / Linux
% ifconfig
```

4. Run the `mock_server.py` code on the server computer:

```
python mock_server.py
```

5. Run the `mock_hololens.py` on the client computer:

```
python mock_client.py
```


## Project Structure

```
avatar-repo/
│
├── Assets/ # Contains all assets for the Unity project, including scenes, scripts, and resources.
│   ├── Scenes/ # Unity scenes for the HoloLens 2 application
│   ├── Scripts/ # All C# and Python scripts for the project
│   │   ├── CSharp/ # C# scripts for Unity and HoloLens 2 interaction
│   │   └── Python/ # Python scripts for any non-Unity functionality
│   └── Resources/ # Any resources (e.g., images, models) used in the project
│
├── MRTK/ # Mixed Reality Toolkit directory with extensions, profiles, and SDK.
│   ├── Extensions/ # Custom extensions for the MRTK
│   ├── Profiles/ # MRTK configuration profiles
│   └── SDK/ # MRTK SDK files
│
├── Tests/ # Test scripts for both C# and Python components of the project
│   ├── CSharp/ # C# unit tests
│   └── Python/ # Python unit tests
│
├── Comms/ # Scripts related to communication testing and setup
│   ├── Deployment/ # Scripts ready for deployment
│   └── Mock/ # Scripts used for debugging and testing on mock setups
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## Contributing

To contribute effectively to this project, perform the following steps:

1. Fork the repository
2. Clone the repo to your local drive

Also some general guidelines, please use as much commenting as possible so the code will be easier for others to read going forward! (P.S. you can use ChatGPT to automatically generate in-line comments for your code)

## TODO 📝

□ Add C# code provided in Lab to repository
□ Add mock mobile robot communication functionality
