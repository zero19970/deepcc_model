# deepcc_model
Provide some deepcc model train with TCGA data
Four kinds of cancer deepcc model are available here.
1. Breast Cancer model was trained with data set from TCGA.
2. a. Colorectal Cancer model was trained with data set from TCGA. 
   b. Another Colorectal Cancer model was trained with data set from TCGA and another 12 data sets from GSE.
3. Gastric Cancer model was trained with data set from ACRG.
4. Ovarian Cancer model was trainde with data set from MAYO.

# load deepcc model
```
load_DeepCC_model <- function(prefix){
  load(file = paste0(prefix, ".RData"))
  classifer <- keras::load_model_hdf5(filepath =paste0(prefix, ".hdf5"))
  list(classifier = classifer, levels = levels)
}

# for CRC model trained with TCGA data
CRC_TCGA <- load_DeepCC_model("CRC_TCGA")
```