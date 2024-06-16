

# Constellation API

Welcome to the Constellation API repository. This API calculates the constellations and key stars directly overhead for different regions of the world and updates this data hourly. It can be used across various platforms, including iOS and Android apps, to fetch star and constellation data based on the user's location.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Usage](#usage)
  - [API Endpoints](#api-endpoints)
  - [Example Requests](#example-requests)
- [Setup and Installation](#setup-and-installation)
  - [Local Development](#local-development)
  - [GitHub Actions](#github-actions)
- [Contributing](#contributing)
- [License](#license)

## Introduction
The Constellation API is designed to provide real-time star and constellation data for different regions. This data can be utilized in applications to display celestial information relevant to the user's current time and location.

## Features
- **Hourly Updates:** The star data is updated every hour.
- **Regional Data:** Provides star and constellation data for multiple predefined regions (e.g., North America, Europe, Asia).
- **Key Stars:** Focuses on key stars in selected constellations for efficient data retrieval and processing.

## Usage
### API Endpoints
- **GET /stars/{region}**: Retrieves the star data for the specified region.
- **GET /constellations/{region}**: Retrieves the constellation data for the specified region.

### Example Requests
- **Fetch star data for North America:**
  ```
  GET /stars/north_america
  ```
  Response:
  ```json
  {
    "timestamp": "2024-06-15T23:29:16.192347",
    "latitude": "40.7128 N",
    "longitude": "74.006 W",
    "star_positions": [
      {
        "star_name": "Sirius",
        "altitude_degrees": -47.98897723628723,
        "azimuth_degrees": 4.083517745576752,
        "distance_au": 8.6
      },
      ...
    ]
  }
  ```

- **Fetch constellation data for Europe:**
  ```
  GET /constellations/europe
  ```
  Response:
  ```json
  {
    "timestamp": "2024-06-15T23:29:16.192347",
    "latitude": "48.8566 N",
    "longitude": "2.3522 E",
    "constellations": [
      {
        "constellation_name": "Orion",
        "stars": ["Betelgeuse", "Rigel"]
      },
      ...
    ]
  }
  ```

## Setup and Installation
### Local Development
To set up the project locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/constellationapi.git
   cd constellationapi
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the script to generate star data:
   ```bash
   python get_constellation_positions.py
   ```

### GitHub Actions
This repository is configured to use GitHub Actions for automated hourly updates. The workflow file is located in `.github/workflows/get_constellation_positions.yml`.

To ensure the GitHub Actions workflow runs correctly:
1. Ensure the repository is public to take advantage of free GitHub Actions minutes.
2. Set the necessary permissions for the workflow to commit and push changes.

## Contributing
Contributions are welcome! Please fork the repository and create a pull request to contribute to this project.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
