# Time Series Analysis Using Bitcoin

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

A hands-on tutorial for forecasting Bitcoin prices with Statsmodels, packaged into two Docker workflows.

## Table of Contents

* [Installation](#installation)
* [Usage](#usage)
* [Project Structure](#project-structure)
* [Docker Workflows](#docker-workflows)

  * [Basic Docker](#basic-docker)
  * [Advanced Docker](#advanced-docker)
* [Contributing](#contributing)
* [License](#license)
* [Authors](#authors)

---

## Installation

### Prerequisites

* **Python 3.8+**
* **Docker** & **Docker Compose** (optional for advanced workflow)
* `git` command-line tool

### Clone the repo

```bash
git clone https://github.com/Rohan-Ambati/Time-Series-Analysis-Using-Bitcoin.git
cd Time-Series-Analysis-Using-Bitcoin
```

---

## Usage

1. **Set up a virtual environment** (if running outside Docker):

   ```bash
   python3 -m venv venv
   source venv/bin/activate    # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

2. **Run the example notebook**:

   ```bash
   jupyter notebook Statsmodels.example.ipynb
   ```

3. **Generate forecasts**:

   * The notebook will output `btc_price_forecast.csv` and plots of actual vs. predicted prices.

---

## Project Structure

```text
.
├── README.md
├── LICENSE
├── requirements.txt
├── statsmodels_utils.py       # data loading, preprocessing, model functions
├── Statsmodels.example.ipynb  # interactive forecasting tutorial
├── Stastmodels.API.ipynb      # wrapping models in Python functions/APIs
├── btc_full_data.xlsx         # raw Bitcoin price data
├── btc_price_forecast.csv     # generated forecasts
├── simple_docker/             # basic Docker environment
│   ├── Dockerfile
│   ├── build.sh
│   ├── run.sh
│   └── clean.sh
└── advanced_docker/           # Python-driven Docker orchestration
    ├── Dockerfile.py
    ├── docker_helpers.py
    ├── build.py
    ├── run.py
    └── config.yaml
```

---

## Docker Workflows

### Basic Docker

A minimal setup using a single `Dockerfile` and bash scripts:

```bash
cd simple_docker
./build.sh      # builds the image
./run.sh        # starts Jupyter at http://localhost:8888
./clean.sh      # removes containers and images
```

Customize the `Dockerfile` with extra Python dependencies or adjust ports in the scripts as needed.

### Advanced Docker

A more modular, Python-driven approach:

```bash
cd advanced_docker
python build.py    # builds the Docker image
python run.py      # starts Jupyter at http://localhost:8888
```

Edit `config.yaml` to set image names, ports, and volume mounts. Extend `docker_helpers.py` and `Dockerfile.py` for additional services or complex workflows.

---

## Contributing

1. Fork this repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

Please follow [PEP8](https://www.python.org/dev/peps/pep-0008/) for code style and include meaningful commit messages.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Authors

* **Rohan Ambati** – *Initial work* – [GitHub profile](https://github.com/Rohan-Ambati)

Feel free to reach out with questions or suggestions!
