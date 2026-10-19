# ResponsibleAI

ResponsibleAI is a collaborative machine-learning project for exploring safer and
more responsible AI systems. The current working implementation is provided as
Jupyter notebooks and uses the [BeaverTails dataset](https://huggingface.co/datasets/PKU-Alignment/BeaverTails),
which contains prompts, responses, safety categories, and safety labels.

## Repository layout

```text
.
├── app/                         # Application entry point (under development)
├── notebooks/
│   ├── MLproject_updated.ipynb  # Main exploratory ML workflow
│   └── responsible_ai.ipynb     # Dataset exploration
└── src/                         # Planned reusable pipeline modules
```

The notebook is the source of truth for the current workflow. The `app/` and
`src/` directories are reserved for the application and reusable training,
prediction, explanation, and preprocessing components as the project evolves.

## Getting started

### Prerequisites

- Python 3.10 or newer
- Jupyter Notebook or JupyterLab
- A Hugging Face account and access to the BeaverTails dataset, if prompted

### Install dependencies

Create and activate a virtual environment, then install the libraries used by
the notebooks:

```bash
python -m venv .venv

# macOS/Linux
source .venv/bin/activate

# Windows PowerShell
.\.venv\Scripts\Activate.ps1

python -m pip install --upgrade pip
python -m pip install datasets pandas numpy scikit-learn
```

The full notebook also includes optional workflows that may require additional
packages such as `transformers`, `torch`, `torchvision`, `Pillow`,
`openai-whisper`, `easyocr`, and `huggingface_hub`. Install only the packages
needed for the cells you intend to run.

### Run the notebooks

```bash
jupyter notebook
```

Open `notebooks/MLproject_updated.ipynb` and run the cells in order. The
notebook loads the BeaverTails dataset with:

```python
from datasets import load_dataset

dataset = load_dataset("PKU-Alignment/BeaverTails")
```

The smaller `notebooks/responsible_ai.ipynb` notebook is useful for initial
dataset inspection.

## Development status

This project is under active development. Training, prediction, explanation,
and preprocessing modules are planned in `src/`, and the application entry
point is planned in `app/`. Until those components are implemented, use the
notebooks for experimentation and results.

## Contributing

Contributions are welcome. Please use a feature branch, keep notebook outputs
manageable, and describe experimental changes and dataset assumptions in the
pull request. Never commit credentials, downloaded datasets, model artifacts,
or other generated files.

## License and dataset terms

This repository does not currently include a license file. Review the
BeaverTails dataset [card](https://huggingface.co/datasets/PKU-Alignment/BeaverTails)
and its terms before downloading or redistributing the dataset or derived
artifacts.
