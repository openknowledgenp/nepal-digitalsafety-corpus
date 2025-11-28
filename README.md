# Nepal Digital Safety Corpus  
*A Multi-Lingual Dataset for Detecting Technology-Facilitated Gender-Based Violence (TFGBV) for Nepal*

This repository contains the **Multilingual Technology-Facilitated Gender-Based Violence (TFGBV) Corpus**, a structured dataset designed to support research on digital harms, abusive behaviors, and gender-based violence expressed in online communication.

The corpus includes **human-generated**, **community-contributed**, and **synthetically augmented** examples across multiple languages (starting with Nepali), annotated for TFGBV categories, abusive terms, and linguistic context.  

It fills a critical gap where existing hate-speech corpora lack gender-specific and technology-enabled forms of abuse, especially for low-resource languages.

**A joint initiative of [Open Knowledge Nepal (OKN)](https://oknp.org/) and [Women Leaders in Technology (WliT)](https://wlit.org/)**



<img width="277" height="79" alt="image" src="https://github.com/user-attachments/assets/a2fb9fa6-dd0e-42ad-8e0c-4627800f387c" />

<br/>
<img width="120" height="120" alt="image" src="https://github.com/user-attachments/assets/c8c07574-75a6-4973-b6b7-806e24c0d9aa" />



---

## 📌 Table of Contents

1. [Background & Motivation](#background--motivation)  
2. [Corpus Overview](#corpus-overview)  
3. [Data Files](#data-files)  
4. [Schema & Fields](#schema--fields)  
5. [TFGBV Subcategories](#tfgbv-subcategories)  
6. [Languages](#languages)  
7. [Data Sources & Annotation](#data-sources--annotation)  
8. [Ethical Considerations](#ethical-considerations)  
9. [License](#license)  
10. [Citation](#citation)  
11. [Contribution Guidelines](#contribution-guidelines)

---

## 🧠 Background & Motivation

Technology-facilitated gender-based violence (TFGBV) includes any digital or technology-enabled behavior that harms, threatens, coerces, humiliates, or targets individuals on the basis of gender.  
While hate-speech datasets exist, few capture:

- threats explicitly tied to gender  
- coercion through digital means  
- sexualized or intimate-image-based harassment  
- culturally specific gendered insults  
- low-resource languages (e.g., Nepali, Mixed Nepali and Hindi, Romanized Nepali)

This corpus aims to fill that gap by providing a **public, multilingual, structured TFGBV dataset** suitable for:

- machine learning classification  
- lexicon development  
- cross-lingual research  
- digital safety interventions  
- academic studies on online harms with a focus on GBV 

---

## 📚 Corpus Overview

- **Total samples:** 10000+ (growing)
- **Formats:** CSV and JSON files
- **Types of data included:**  
  - Annotated abusive and non-abusive text  
  - Lexicons of gendered slurs and TFGBV expressions  
  - Synthetic samples for low-resource subcategories  
- **Languages:** Nepali, Newari, Tharu... + future expansion
- **Labels:** TFGBV vs non-TFGBV, subcategory classification

The dataset will evolve as more contributors and annotators participate.

---

## 📁 Data Files

### `tfgbv_lexicon.csv`
A multilingual list of abusive terms, categorized by TFGBV subcategory.

Example:
|language | subcategory | term |
| --------- | ----------- | ------- |
| nepali |strong_slurs | राँडी |


---

### `annotated_tfgbv_dataset.csv`  
Annotated TFGBV dataset with full sentences/messages.

Example:
|text|label|language|subcategory|term_used|
| --- | ---| -------| ----------| ---------|
|hey dekhai de छुँदै छुँदै|1|nepali_generated|coercive_threat|छुँदै छुँदै|
|yo manche नांगीन ho timi | 1 |nepali|gendered_insults|नांगीन|


---

## 🧱 Schema & Fields

### **Lexicon File Fields**

| Field | Description |
|-------|-------------|
| `language` | Language of the term |
| `subcategory` | TFGBV category (e.g., strong_slurs, coercive_threat) |
| `term` | Actual abusive term/slur |

---

### **Dataset Fields**

| Field | Description |
|-------|-------------|
| `text` | Full message or sentence |
| `label` | 1 = TFGBV, 0 = non-TFGBV |
| `language` | e.g., nepali, romanized_nepali, newari, etc. |
| `subcategory` | TFGBV type (defined below) |
| `term_used` | Term found in text (optional) |

---

## 🏷️ TFGBV Subcategories

Below are the defined categories currently used in the corpus. These may evolve over time.

| Subcategory | Description |
|------------|-------------|
| **strong_slurs** | Highly offensive, explicit gendered slurs used to degrade or demean. |
| **slurs** | General abusive slurs (not always gender-specific) appearing in harmful contexts. |
| **gendered_insults** | Insults targeting someone's gender, gender expression, or identity. |
| **gendered** | Phrases or terms that implicitly or explicitly target a gender without being full insults. |
| **sexual_phrases** | Sexual expressions or references that may be non-consensual, objectifying, or harmful depending on context. |
| **sexualized** | Language that sexualizes, objectifies, or targets a person with unwanted sexual overtones. |
| **contextual_phrases** | Phrases that may not be abusive by themselves but become harmful in TFGBV contexts. |
| **contexts** | Messages where context indicates TFGBV, even if explicit slurs are not present. |
| **dehumanizing** | Language that reduces a person to an object, animal, or non-human entity. |
| **coercive_threat** | Attempts to intimidate, force, threaten, or manipulate someone through digital means. |
| **body_shaming** | Derogatory comments about body, appearance, skin, or physical attributes. |
| **hybrid** | Messages containing multiple overlapping TFGBV forms (e.g., slur + threat, sexual phrase + insult). |

---

## 🌍 Languages

The dataset currently includes:

- **Nepali (nepali)**
- **Nepali (romanized)**
- **Newari**
- **Bhojpuri**
- **Tharu**
- **Tamang**

Upcoming expansions:

- More local languages practiced in Nepal   

Feel free to suggest additional languages.

---

## 📝 Data Sources & Annotation

The corpus was created through a combination of:

### Human-generated fictional examples  
Created by volunteers representing realistic TFGBV scenarios.

### Community-contributed samples  
Curated text contributions that mimic or anonymize real experiences.

All samples undergo:

- Manual review by at least one annotator  
- Category and subcategory labeling  
- Language verification

Future versions may include inter-annotator agreement metrics (e.g., Cohen’s kappa).

---

## ⚖️ Ethical Considerations

This dataset contains **sensitive and harmful language**.

To minimize harm:

- Real personal identifiable information is omitted or fictionalized.
- Synthetic examples are clearly marked.
- Content is for **research and safety purposes only**, not for generating abusive text.
- Users must ensure downstream models include **safeguards** to avoid misuse.

Researchers should implement filters and ethical controls when training or deploying models using this corpus.

---

## 📄 License

This corpus is released under the **CC0 1.0 Universal Public Domain Dedication**.

You may use, modify, distribute, or build upon the dataset **for any purpose**, including commercial and non-commercial use, **without requiring permission or attribution**.

While attribution is not legally required under CC0, it is always appreciated as it helps support and acknowledge the work of the contributors.
---

## 📚 Citation

If you use this dataset, please cite it as:

```bibtex
@dataset{nepal-digitalsafety-corpus2025,
  title={Nepal Digital Safety Corpus},
  author={Open Knowledge Nepal (OKN), Women Leaders in Technology (WLiT)},
  year={2025},
  url={[https://github.com/yourrepo/tfgbv-corpus](https://github.com/openknowledgenp/nepal-digitalsafety-corpus)}
}

