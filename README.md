[![License: AGPL v3](https://img.shields.io/github/license/SDM-TIB/ckanext-TIBimport?color=blue)](LICENSE)

[![CKAN](https://img.shields.io/badge/ckan-2.9-orange.svg?style=flat)](https://github.com/ckan/ckan)

# TIBimport

`ckanext-TIBimport` is a comprehensive CKAN extension that enables seamless integration and automated import of research datasets from multiple academic and scientific data repositories. It facilitates the aggregation of research data from various sources into a unified CKAN-based data management system.

## Supported Repositories

| Repository | Institution | Protocol |
|---|---|---|
| **LUH** | Leibniz University Hannover | CKAN API |
| **Leuphana** | University Lüneburg | OAI-PMH + DataCite |
| **Göttingen Research Online** | University of Göttingen | Dataverse API |
| **OSNADATA** | University of Osnabrück | OAI-PMH DataCite |
| **LEOPARD** | TU Braunschweig | OAI-PMH |
| **RADAR** | — | RADAR API |
| **PANGAEA** | — | OAI-PMH (topic-filtered) |

## Key Features

- **Automated Import Workflows**: Scheduled and on-demand dataset imports with comprehensive logging and error handling
- **Flexible Parser Profiles**: Modular architecture with specialized parser profiles for each repository type
- **Background Job Processing**: Utilizes CKAN's background job system for efficient large-scale data imports
- **Virtual Dataset Management**: Support for virtual datasets with configurable ribbon displays
- **Notification System**: Integration with TIBnotify plugin for import status notifications
- **Comprehensive Logging**: Detailed import summaries and error tracking

## Technical Architecture

The plugin implements a modular parser-based architecture where each supported repository has its own specialized parser profile. The system supports the following data exchange protocols:

- OAI-PMH (Open Archives Initiative Protocol for Metadata Harvesting)
- DataCite API
- Dataverse API
- Direct CKAN API integration

## Requirements

| CKAN version    | Compatibility |
|-----------------|---------------|
| 2.8 and earlier | No            |
| 2.9             | Yes           |
| 2.10 and later  | Untested      |

- Python 3.6+
- Required Python packages (see `requirements.txt`)

## Installation

As usual for CKAN extensions, you can install `ckanext-TIBimport` as follows:

```bash
git clone git@github.com:SDM-TIB/ckanext-TIBimport.git
pip install -e ./ckanext-TIBimport
pip install -r ./ckanext-TIBimport/requirements.txt
```

Then, add `TIBimport` to the `ckan.plugins` setting in your CKAN config file:
   ```ini
   ckan.plugins = ... TIBimport
   ```

## Configuration

Add the following settings to your CKAN config file (`ckan.ini`):

```ini
# Path to the directory where import log files are written.
# (optional, default: /usr/lib/ckan/default/src/ckanext-TIBimport/ckanext/tibimport/logs/)
tibimport.log_file_path = /path/to/logs/
```

## Documentation

📚 Complete documentation is available in the [`documentation/`](documentation/) directory, covering:

- **System Documentation** – Technical specifications, architecture, and API details
- **User Documentation** – User guides and operational procedures
- **Lower Saxony Repositories Documentation** – Specialized documentation for academic repository integrations

## Testing

To run the tests:

```bash
pytest --ckan-ini=test.ini
```

To run the tests and produce a coverage report:

```bash
pytest --ckan-ini=test.ini --cov=ckanext.tibimport
```

## Support

For technical documentation, usage guides, and integration details, please refer to the comprehensive documentation in the [`documentation/`](documentation/) directory.

## License

`ckanext-TIBimport` is licensed under AGPL-3.0, see the [license file](LICENSE).
