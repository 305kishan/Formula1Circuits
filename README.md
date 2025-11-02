# Formula 1 Circuits Dataset

## Overview

This dataset contains comprehensive information about all Formula 1 circuits that have hosted Grand Prix races from the inaugural 1950 season through 2025. The dataset includes 77 unique circuits with detailed information about their specifications, racing history, and lap records.

## Dataset Information

- **File Name**: `circuits.csv`
- **Format**: CSV (Comma-Separated Values)
- **Encoding**: UTF-8
- **Rows**: 77 circuits (excluding header)
- **Last Updated**: Data collected as of 2025 season

## Data Source

**Primary Source**: [Pitwall.app](https://pitwall.app/circuits)

Pitwall.app is a comprehensive Formula 1 statistics and information website that aggregates data from official F1 sources, historical records, and race archives.

## Collection Method

The dataset was collected through web scraping using the following methodology:

1. **Initial Data Collection**: 
   - Fetched the main circuits listing page from `https://pitwall.app/circuits`
   - Extracted basic circuit information (name, location, last race, number of races)

2. **Detailed Data Extraction**:
   - For each circuit, visited individual circuit detail pages
   - Extracted additional information including:
     - Circuit type (Race, Street, Road)
     - First and last Grand Prix events
     - Track specifications (length, turns, direction)
     - Lap records (timing, driver, year)

3. **Technical Implementation**:
   - **Tools**: Python 3.10.4
   - **Libraries**: 
     - `requests` for HTTP requests
     - `beautifulsoup4` for HTML parsing
     - `pandas` for data processing
     - `concurrent.futures.ThreadPoolExecutor` for parallel processing
   - **Method**: Multithreaded web scraping (20 concurrent workers) for efficient data collection
   - **Data Processing**: Automated parsing, cleaning, and transformation of raw HTML data into structured CSV format

4. **Data Transformation**:
   - Separated location into City and Country columns
   - Parsed lap record format to extract timing, driver name, and year separately
   - Converted lap times to seconds for numerical analysis
   - Standardized column names and data types

## Dataset Schema

The dataset contains the following columns:

| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `Circuit` | String | Official name of the circuit | "Silverstone Circuit" |
| `City` | String | City where the circuit is located | "Silverstone" |
| `Country` | String | Country where the circuit is located | "United Kingdom" |
| `Track Length (km)` | Float | Length of the circuit in kilometers | 5.891 |
| `Turns` | Integer | Number of turns on the circuit | 18 |
| `Direction` | String | Racing direction | "Clockwise" or "Anti clockwise" |
| `Circuit Type` | String | Classification of circuit | "Race", "Street", or "Road" |
| `First Grand Prix` | String | Name and year of first F1 Grand Prix held | "1950 British Grand Prix" |
| `Last Grand Prix` | String | Name and year of most recent F1 Grand Prix held | "2025 British Grand Prix" |
| `Races` | Integer | Total number of Formula 1 Grand Prix races held | 60 |
| `Best Lap Timing` | String | Fastest lap time in MM:SS.mmm format | "1:09.832" |
| `Best Lap Driver` | String | Name of the driver who set the lap record | "Nigel Mansell" |
| `Best Lap Year` | Integer | Year when the lap record was set | 1987 |
| `Best Lap Time` | Float | Lap record converted to seconds | 69.832 |

## Data Quality Notes

- **Circuit Type Classifications**:
  - **Race**: Purpose-built racing circuits
  - **Street**: Temporary street circuits (often in urban areas)
  - **Road**: Public roads used for racing (historical circuits)

- **Historical Context**: Some circuits have very different configurations in different eras. The data reflects the most recent or most commonly used configuration.

- **Lap Records**: Lap records represent the fastest lap times recorded during official Formula 1 Grand Prix races and may differ from other racing series records.

- **Missing Data**: Some historical circuits may have incomplete information due to limited historical records.

## Usage

This dataset is suitable for:
- Formula 1 historical analysis and research
- Circuit characteristics analysis
- Performance trend analysis
- Geographic distribution studies
- Data visualization projects
- Machine learning applications (e.g., predicting circuit performance)

## License & Citation

This dataset is compiled from publicly available information on Pitwall.app. When using this dataset, please:

1. **Credit the original source**: [Pitwall.app](https://pitwall.app)
2. **Credit the dataset creator**: If using this specific compiled dataset, please reference this repository
3. **Respect rate limits**: If collecting data from Pitwall.app directly, ensure reasonable request rates

## Disclaimer

- This dataset is provided for educational and research purposes
- Data accuracy depends on the source website and may contain errors
- Always verify critical information from official Formula 1 sources
- The dataset creator assumes no responsibility for data accuracy or completeness

## Technical Details

- **Collection Script**: Available in `circuits.ipynb` (Jupyter Notebook)
- **Python Version**: 3.10.4
- **Collection Date**: 2025 (specific date not recorded)
- **Processing Time**: Approximately 15-20 minutes for 77 circuits (with multithreading)

## Updates

This dataset is manually collected and may not reflect real-time updates. For the most current information, please refer to:
- Official Formula 1 website: [Formula1.com](https://www.formula1.com)
- Pitwall.app: [pitwall.app](https://pitwall.app)

## Contributing

If you notice any errors, missing circuits, or outdated information, please open an issue or submit a pull request with corrections.

