## Overview  
---
The QALB-2014-L1 dataset, sourced from the QALB project, is designed to support research in Arabic grammatical error correction. It includes a rich collection of annotated texts, arranged into training, development, and testing sets to aid in the development and testing of machine learning models for Arabic natural language processing.

---

## Dataset Contents
---
* QALB-2014-L1-Train/Test/Dev`.column`: These files provide comprehensive annotations for Arabic words, highlighting their morphological features and grammatical properties, including parts of speech and lemmas.
      
* QALB-2014-L1-Train/Test/Dev`.cor`: These files contain the finalized, corrected versions of Arabic sentences, which serve as benchmarks for evaluating the performance of text correction technologies.
  
* QALB-2014-L1-Train/Test/Dev`.m2`: Error annotations and corrections in `.m2` format, used for training and testing grammatical error correction systems.
  
* QALB-2014-L1-Train/Test/Dev`.sent`: Includes Arabic sentences with potential grammatical errors for text correction tasks, with **19,411** sentences in Train, **1,017** in Dev, and **968** in Test.

- **Train:**    
  The **training set** is used to develop Arabic grammatical error correction models. It includes a substantial number of original sentences paired with corrections and error annotations, allowing models to learn common grammatical mistakes and their appropriate remedies.

- **Development (Dev):**    
  The **development set** is used to fine-tune model parameters and evaluate intermediate performance. It helps prevent overfitting and ensures good generalization to unseen data.

- **Test:**    
  The **test set** is used to evaluate the final performance of trained models, offering an unbiased assessment of how effectively they correct grammatical errors in new, unseen Arabic text.
---
## Sample Data
---
[column Sample](Dev/QALB-2014-L1-Dev.column)  
[cor Sample](Dev/QALB-2014-L1-Dev.cor)  
[m2 Sample](Dev/QALB-2014-L1-Dev.m2)  
[sent Sample](Dev/QALB-2014-L1-Dev.sent)  
   
---
## Type of annotation in m2 
---
| **Type**      | **Annotation**                                                      | **Explanation**                                                                 |
|---------------|---------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **Edit**      | A 0 1\|\|\|Edit\|\|\|إلى\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                           | Change the text at position 0 to "إلى".                                         |
| **Delete**    | A 39 40\|\|\|Delete\|\|\|\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                         | Remove the text between positions 39 and 40.                                    |
| **Add_before**| A 4 4\|\|\|Add_before\|\|\|:\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                      | Insert a colon (:) before the text at position 4.                               |
| **Add_after** | A 62 62\|\|\|Add_after\|\|\|؟\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                     | Insert a question mark (?) after the text at position 62.                       |
| **Merge**     | A 6 8\|\|\|Merge\|\|\|ومن\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                         | Combine the text from positions 6 to 8 into "ومن".                              |
| **Split**     | A 43 44\|\|\|Split\|\|\|لا فرق\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                    | Split the text at positions 43 to 44 into separate parts.                       |
| **Move**      | A 30 32\|\|\|Move\|\|\|هؤلاء الإرهابيون\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0           | Move the text "هؤلاء الإرهابيون" from positions 30 to 32 to another location.   |
| **Other**     | A 22 24\|\|\|Other\|\|\|وما الذي\|\|\|REQUIRED\|\|\|-NONE-\|\|\|0                  | Represents an unspecified or unique correction action involving the text "وما الذي". |


---



## Data Access
---
To access the datasets you had to request it from the following link:
- Qalb Dataset: [Click To Request](https://docs.google.com/forms/d/e/1FAIpQLScSsuAu1_84KORcpzOKTid0nUMQDZNQKKnVcMilaIZ6QF-xdw/viewform)
---
