# CNC Assist Corpus

Welcome to the CNC Assist Corpus repository! This repository contains a compiled corpus designed to support CNC programming, offering a comprehensive set of question-answer pairs and procedural instructions in both Spanish and Basque.

## Contents

The corpus is divided into two main subsets:

1. **Question-Answering Subset**: A bilingual collection of question-answer pairs covering a range of topics related to CNC programming.
2. **Procedures Subset**: A series of step-by-step procedures, also bilingual, detailing various tasks involved in CNC programming.

## Repository Structure

The repository is organized into the following folders:

- **`QA_corpus.json`**: Contains a JSON file listing all question-answer pairs in both Spanish and Basque.
- **`QA_images/`**: A folder containing images associated with the question-answer pairs.
- **`PROCEDURES_corpus.json`**: Contains a JSON file listing all procedures in both Spanish and Basque.
- **`PROCEDURES_images/`**: A folder containing images associated with the procedures.

## Data Compilation

### 1. Question-Answering Subset

This subset includes questions and answers based on the Spanish version of a reference technical manual for milling machines. The process for compiling this subset includes:

- **Conversion**: The technical manual was converted from PDF to a machine-readable HTML format.
- **Processing**: Textual data was cleaned and organized into JSON format.
- **Annotation**: Using the CrowdZientzia platform, bilingual technical experts annotated questions, categorized them into "generic" or "specific", and provided both original and improved answers.
- **Translation**: The question-answer pairs were translated into Basque.

#### Files

- **`QA_corpus.json`**: Contains the question-answer pairs. Each entry includes:
  - **es** (Spanish) and **eu** (Basque) versions of the question and answer.
  - **question**: The question text.
  - **question_variations**: Variations of the question.
  - **answer**: The raw answer text.
  - **html_answer**: HTML-structured answer (for generic questions).
  - **improved_answer**: Enhanced answer provided by annotators.
  - **type**: The question type ("generic" or "specific").
  - **image**: Associated images, if any.

- **`QA_images/`**: Contains images referenced in the `QA_corpus.json` file. Each image is linked to a question-answer pair.


#### Example

```json
{
  "id": "<HASH0>",
  "es": {
    "question": "¿Para qué se utiliza la letra F?",
    "question_variations": ["¿Tiene algo que ver la letra F con el avance de los ejes?"],
    "answer": "·F· Avance de los ejes. El avance se representa mediante la letra F seguida del valor de avance deseado.",
    "html_answer": "",
    "improved_answer": "Se utiliza para programar o modificar el valor del avance de herramienta."
  },
  "eu": {
    "question": "Zertarako erabiltzen da F hizkia?",
    "question_variations": ["F hizkiak ardatzen aintzinapenarekin zerikusirik du?"],
    "answer": "·F· Ardatzen aintzinapena. Aintzinapena F letraren bidez adierazten da, eta, ondoren, lortu nahi den aintzinapen-balioa.",
    "html_answer": "",
    "improved_answer": "Erramintaren aintzinapena aldatu edo programatzeko erabiltzen da."
  },
  "type": "specific",
  "image": ["https://example.com/spe-image.png"]
}
```

### 2. Procedures Subset

This subset comprises procedural instructions detailing various tasks involved in CNC programming. It includes:

- **Identification**: Procedures were identified and annotated by bilingual technical experts.
- **Compilation**: Procedures were organized into JSON format using a custom GUI.
- **Linking**: Procedures include links to related procedures when necessary.

#### Files

- - **`PROCEDURES_corpus.json`**: Contains the procedural instructions. Each entry includes:
  - **es** (Spanish) and **eu** (Basque) versions of the procedure.
  - **title**: The title of the procedure.
  - **introduction**: Optional introductory text.
  - **additional_info**: Extra information like images.
  - **methods**: Different methods to perform the procedure.
  - **steps**: A series of steps involved in the procedure.
  - **step_description**: Description of each step.
  - **nesting**: Links to nested procedures if applicable.

- **`PROCEDURES_images/`**: Contains images referenced in the 'PROCEDURES_corpus.json' file. Each image is linked to a procedural instruction.
- 
#### Example

```json
{
  "id": "<HASH1>",
  "es": {
    "title": "Editar o modificar un programa",
    "introduction": "",
    "additional_info": [],
    "methods": [{
      "_id": 0,
      "title": "",
      "steps": [{
        "_id": 0,
        "title": "Abrir el programa deseado.",
        "step_description": "",
        "additional_info": [],
        "nesting": "<HASH2>"
      },{
        "_id": 1,
        "title": "Con el programa en pantalla, tal y como se muestra en la siguiente imagen, se podrá comenzar a modificar o extender el código G para programar la pieza.",
        "step_description": "",
        "additional_info": ["https://example.com/image.png"],
        "nesting": ""
      }]
    }]
  },
  "eu": {
    "title": "Programa bat editatu edo aldatu",
    "introduction": "",
    "additional_info": [],
    "methods": [{
      "_id": 0,
      "title": "",
      "steps": [{
        "_id": 0,
        "title": "Erabili nahi den programa zabaldu.",
        "step_description": "",
        "additional_info": [],
        "nesting": "<HASH2>"
      },{
        "_id": 1,
        "title": "Programa pantailan edukita, hurrengo irudian erakusten den bezala, G kodea aldatzen edo hedatzen hasi ahal izango da pieza programatzeko.",
        "step_description": "",
        "additional_info": ["https://example.com/image.png"],
        "nesting": ""
      }]
    }]
  }
}
```

## References

This corpus is part of the research presented in the paper titled "Towards the Development of a Conversational CNC Assistant: Compiling a Sample of Key Questions and Procedures for Benchmarking Purposes". The paper will be published as part of the proceedings of the International Conference on Industry 4.0 and Smart Manufacturing (ISM 2024).

## Contributing

Contributions to the corpus are welcome! If you have suggestions for additional question-answer pairs or procedures, or if you notice any errors, please open an issue or submit a pull request.

## License

The resources in this repository are licensed under the Creative Commons Attribution-ShareAlike 3.0 Spain License. To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/es/ or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

## Contact

For any questions or inquiries, please contact [magirre@vicomtech.org](mailto:magirre@vicomtech.org).

---

Thank you for using the CNC Assist Corpus! We hope this resource aids in your CNC programming endeavors.
