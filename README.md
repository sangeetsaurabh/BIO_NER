# NER demo using BioBert

Recognize Bio Medical Named Entity using Biobert transformer

## Input Data

Labelled NER Data can be downloaded using https://github.com/cambridgeltl/MTL-Bioinformatics-2016.

To demo the model,  BC5CDR and BioNLP13CG datasets were used.

BC5CDR tags :-

    'B-Chemical', 
    'O', 
    'B-Disease', 
    'I-Disease', 
    'I-Chemical'
    
BioNLP13CG tags :-

    'B-Anatomical_system',
    'B-Cancer',
    'B-Cell', 
    'B-Cellular_component',
    'B-Developing_anatomical_structure',
    'B-Gene_or_gene_product', 
    'B-Immaterial_anatomical_entity',
    'B-Multi-tissue_structure',
    'B-Organ',
    'B-Organism', 
    'B-Organism_subdivision',
    'B-Organism_substance',
    'B-Pathological_formation', 
    'B-Simple_chemical',
    'B-Tissue',
    'I-Amino_acid',
    'I-Anatomical_system',
    'I-Cancer', 
    'I-Cell',
    'I-Cellular_component',
    'I-Developing_anatomical_structure',
    'I-Gene_or_gene_product', 
    'I-Immaterial_anatomical_entity',
    'I-Multi-tissue_structure',
    'I-Organ',
    'I-Organism', 
    'I-Organism_subdivision',
    'I-Organism_substance',
    'I-Pathological_formation',
    'I-Simple_chemical', 
    'I-Tissue',
    'O'

## Results

Both datasets generated excellent results, with more than 95% accuracy. Considering these datasets were small, the results produced were excellent.

#### BC5CDR results -

                    precision    recall  f1-score   support

               O       0.99      0.98      0.98    110576
      B-Chemical       0.92      0.89      0.90      5385
       B-Disease       0.80      0.82      0.81      4424
       I-Disease       0.69      0.80      0.74      2737
      I-Chemical       0.79      0.86      0.82      1628

        accuracy                           0.97    124750
       macro avg       0.84      0.87      0.85    124750
    weighted avg       0.97      0.97      0.97    124750


#### BioNLP13CG results -

For the entities that have a reasonable number of samples, the results generated were good. But the entities that have a few training samples didn't produce good results. 


                                         precision    recall  f1-score   support

                         B-Amino_acid       1.00      0.06      0.12        62
                  B-Anatomical_system       0.00      0.00      0.00        17
                             B-Cancer       0.84      0.86      0.85       924
                               B-Cell       0.84      0.86      0.85      1013
                 B-Cellular_component       0.74      0.48      0.58       180
    B-Developing_anatomical_structure       0.00      0.00      0.00        17
                 B-Gene_or_gene_product     0.88      0.93      0.90      2520
         B-Immaterial_anatomical_entity     0.67      0.13      0.22        31
             B-Multi-tissue_structure       0.58      0.72      0.64       303
                              B-Organ       0.65      0.35      0.46       156
                           B-Organism       0.83      0.82      0.83       518
               B-Organism_subdivision       0.00      0.00      0.00        39
                 B-Organism_substance       0.63      0.26      0.37       102
             B-Pathological_formation       0.67      0.16      0.26        88
                    B-Simple_chemical       0.82      0.76      0.79       727
                             B-Tissue       0.56      0.49      0.52       184
                         I-Amino_acid       0.00      0.00      0.00         3
                  I-Anatomical_system       0.00      0.00      0.00         9
                             I-Cancer       0.83      0.85      0.84       604
                               I-Cell       0.89      0.88      0.89      1091
                 I-Cellular_component       0.80      0.51      0.62        69
    I-Developing_anatomical_structure       0.00      0.00      0.00         4
               I-Gene_or_gene_product       0.88      0.92      0.90      2354
       I-Immaterial_anatomical_entity       0.00      0.00      0.00        10
             I-Multi-tissue_structure       0.71      0.79      0.75       162
                              I-Organ       0.00      0.00      0.00        17
                           I-Organism       0.85      0.53      0.66       120
               I-Organism_subdivision       0.00      0.00      0.00         9
                 I-Organism_substance       0.00      0.00      0.00        24
             I-Pathological_formation       0.67      0.05      0.10        39
                    I-Simple_chemical       0.90      0.79      0.84       622
                             I-Tissue       0.62      0.52      0.57       111
                                    O       0.98      0.99      0.98     40642

                             accuracy                           0.95     52771
                            macro avg       0.54      0.42      0.44     52771
                         weighted avg       0.94      0.95      0.94     52771


## How did the models perform?

In order to understand the performance, same results were generated using sciSpacy. Here are the results from sciSpacy -

#### BC5CDR results using sciSpacy -

                    precision    recall  f1-score   support

             O       0.98      0.98      0.98    110576
    B-Chemical       0.91      0.88      0.90      5385
     B-Disease       0.82      0.81      0.81      4424
     I-Disease       0.74      0.74      0.74      2737
    I-Chemical       0.63      0.57      0.60      1628

      accuracy                           0.96    124750
     macro avg       0.82      0.80      0.81    124750
    weighted avg     0.96      0.96      0.96    124750
    
#### BioNLP13CG results using sciSpacy -


                                            precision    recall  f1-score   support

                                    O       0.97      0.97      0.97     40642
                         B-Amino_acid       0.00      0.00      0.00        62
                  B-Anatomical_system       0.00      0.00      0.00        17
                             B-Cancer       0.80      0.76      0.78       924
                               B-Cell       0.78      0.75      0.77      1013
                 B-Cellular_component       0.76      0.74      0.75       180
    B-Developing_anatomical_structure       0.00      0.00      0.00        17
               B-Gene_or_gene_product       0.87      0.85      0.86      2520
       B-Immaterial_anatomical_entity       0.55      0.19      0.29        31
             B-Multi-tissue_structure       0.73      0.68      0.70       303
                              B-Organ       0.64      0.59      0.61       156
                           B-Organism       0.85      0.82      0.83       518
               B-Organism_subdivision       1.00      0.03      0.05        39
                 B-Organism_substance       0.78      0.57      0.66       102
             B-Pathological_formation       0.81      0.33      0.47        88
                    B-Simple_chemical       0.75      0.69      0.72       727
                             B-Tissue       0.53      0.64      0.58       184
                         I-Amino_acid       0.00      0.00      0.00         3
                  I-Anatomical_system       0.00      0.00      0.00         9
                             I-Cancer       0.69      0.60      0.64       604
                               I-Cell       0.71      0.63      0.67      1091
                 I-Cellular_component       0.55      0.45      0.50        69
    I-Developing_anatomical_structure       0.00      0.00      0.00         4
               I-Gene_or_gene_product       0.73      0.77      0.75      2354
       I-Immaterial_anatomical_entity       0.00      0.00      0.00        10
             I-Multi-tissue_structure       0.65      0.66      0.65       162
                              I-Organ       0.00      0.00      0.00        17
                           I-Organism       0.13      0.48      0.21       120
               I-Organism_subdivision       0.00      0.00      0.00         9
                 I-Organism_substance       0.03      0.08      0.04        24
             I-Pathological_formation       0.33      0.03      0.05        39
                    I-Simple_chemical       0.51      0.47      0.49       622
                             I-Tissue       0.57      0.46      0.51       111

                             accuracy                           0.91     52771
                            macro avg       0.48      0.40      0.41     52771
                         weighted avg       0.91      0.91      0.91     52771
                         
 Biobert model performed better than sciSpacy with both BC5CDR and BioNLP13CG datasets.


