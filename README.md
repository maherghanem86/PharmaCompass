PharmaCompass: Neuro-Symbolic Information Extraction & Clinical Trial Matching

PharmaCompass is an end-to-end hybrid Neuro-Symbolic AI framework designed to bridge the gap between unstructured clinical text and formal semantic knowledge bases. By combining the generative power of fine-tuned Large Language Models (LLMs) with the strict deductive capabilities of Web Ontology Language (OWL) ontologies, PharmaCompass automates medical data extraction and accurately matches patient profiles to complex clinical trials.

🌟 Key Features

Generative Information Extraction: Fine-tuned Llama-2-7B using QLoRA (4-bit quantization) on MIMIC-III discharge summaries to produce structured, verifiable medical profiles in JSON format.

Robust Knowledge Graph Population: Automated pipelines built with owlready2 that ingest parsed model predictions, execute validation checks, and populate a semantic medical ontology (.owl).

Description Logic Reasoning: Integrates the HermiT Reasoner to run automated logical inference across patient attributes, dynamically filtering and matching eligible candidates for targeted clinical trial criteria.

Interactive Prototype: Features a full-fledged GUI powered by Gradio for real-time clinical text processing, extraction, and trial eligibility checking.

Academic Evaluation: Rigorously tested using Gold Standard benchmarks with fully tracked metrics (Precision, Recall, F1-Score).

🛠️ System Architecture Diagram & Pipeline

The PharmaCompass pipeline consists of four major sequential stages:

Fine-Tuning & Inference: Unstructured patient records $\rightarrow$ Quantized Llama-2-7B Adapter $\rightarrow$ Structured JSON Output.

Ontology Ingestion: JSON Parser $\rightarrow$ Instantiation of Classes (Patients, Medications, Conditions) $\rightarrow$ Populated Ontology.

Semantic Inference: Populated OWL File $\rightarrow$ HermiT Reasoner DL Execution $\rightarrow$ Logical Classification.

Clinical Matching: Execution of Trial Rules $\rightarrow$ Verified Cohort Identification.



📂 Repository Structure

data/

gold_standard_input.csv (Ground-truth verification samples)

my_model_predictions_improved.csv (Extracted clinical metadata in JSON format)

PharmaCompass.owl (The core Semantic Knowledge Graph / Ontology)

notebooks/

Training_Code.ipynb (Llama-2-7B Peft/QLoRA fine-tuning script)

Ontology_Population.ipynb (Dynamic OWL population pipeline)

Full_Automation_Reasoning_Matching.ipynb (HermiT reasoning engine runner)

Evaluation_and_Plotting.ipynb (Statistical grading & graph generation)

PharmaCompass_Final_Prototype.ipynb (Interactive Gradio dashboard code)

images/

metrics_heatmap.png (Precision-Recall breakdown matrix)

performance_bar_chart.png (Overall macro-metric evaluation)

radar_chart.png (Multi-category feature performance comparison)

requirements.txt (Python dependencies)

README.md (Project documentation)




📊 Evaluation & Performance

The model's information extraction precision, stability, and rule-matching accuracy were evaluated comprehensively. The performance metrics across varying clinical categories are visualized below:

Metric Heatmap

Performance Overview





Multi-Axis Capability Assessment

The system demonstrates balanced semantic extraction depth across complex criteria fields:

🚀 Installation & Quick Start

Clone the Repository:

git clone https://github.com/maherghanem86/PharmaCompass.git
cd PharmaCompass


Install Dependencies:

pip install -r requirements.txt


Explore Notebooks:

Run notebooks/Training_Code.ipynb to view or replicate the LLM fine-tuning process.

Run notebooks/PharmaCompass_Final_Prototype.ipynb to spin up the local Gradio dashboard.

🔗 Model Weights Access

The specialized fine-tuned adapter weights for Llama2-7B-MIMIC-iii-Extraction-v1 are hosted on Hugging Face. You can access and utilize the model directly in your environment from:
👉 maherghanem86/PharmaCompass

📄 License & Ethical Disclaimers

This repository is tailored for educational and academic research evaluation. The datasets utilized for training are derived from the de-identified MIMIC-III database. Accessing or executing the model over actual real-world patient data requires strict adherence to institutional data-use agreements and HIPAA certifications.
