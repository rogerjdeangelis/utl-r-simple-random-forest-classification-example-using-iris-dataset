# utl-r-simple-random-forest-classification-example-using-iris-dataset
R simple random forest classification example using iris datase 
    /*                                                                                                                                                                            
                                                                                                                                                                                  
    R simple random forest classification example using iris datase                                                                                                               
                                                                                                                                                                                  
    github                                                                                                                                                                        
    https://tinyurl.com/ycgtmw2f                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset                                                                       
                                                                                                                                                                                  
    R simple random forest classification example using iris datase                                                                                                               
                                                                                                                                                                                  
    What you need to know about a randomforest of trees before you start.                                                                                                         
    ====================================================================                                                                                                          
                                                                                                                                                                                  
    Unlike CART, Logistic, and most models, randomforest does not provide insight into                                                                                            
    your data. It is primarily a black box with bootstrapping and randomly selected and averaged                                                                                  
    variables and subsets of the data. It often 'averages' 1,000 pf decision trees.                                                                                               
                                                                                                                                                                                  
    Roger DeAngelis                                                                                                                                                               
                                                                                                                                                                                  
    "Trees in RF and single trees are built using the same algorithm (usually CART).                                                                                              
    The only minor difference is that a single tree tries all predictors at each split,                                                                                           
    whereas trees in RF only try a random subset of the predictors at each split                                                                                                  
    (this creates independent trees). Also, each tree in a RF is built on a bootstrap                                                                                             
    sample of the training data, rather than on the full training                                                                                                                 
    data set. This makes each tree in the forest an expert on                                                                                                                     
    some domains of the data space, and bad elsewhere.                                                                                                                            
                                                                                                                                                                                  
    So, for these reasons, it makes no sense to extract a single tree                                                                                                             
    from a Random Forest in order to use it as a classifier. Depending on its domains of expertise,                                                                               
    it could give you better results than a traditional tree built with CART on the full dataset,                                                                                 
    or much worse. The thing that allows a RF to be much better than a single tree is that                                                                                        
    it grows many decorrelated trees and averages their output. Only when the committee                                                                                           
    of ensemble of treesnas enough members (usually between 200 and 2000) is variance reduced.                                                                                    
    But individually, each tree of a RF would be weaker than a single tree built via traditional CART."                                                                           
                                                                                                                                                                                  
    Antoine                                                                                                                                                                       
    https://tinyurl.com/y9uznf5s                                                                                                                                                  
    https://stats.stackexchange.com/users/71672/antoine                                                                                                                           
                                                                                                                                                                                  
    Even though Python has popular statistical packages, I prefer R. Primarily becaose of                                                                                         
    very skilled statisticians and programmers behind R.                                                                                                                          
                                                                                                                                                                                  
       Frank Harrel     ASA Fellow Professor of Biostatistics Vanderbuilt Founding Chair                                                                                          
       Brian Ripley     Phd Guy Medal Royal Statistical Society Applied Stat U of Oxford(past)                                                                                    
       Duncan Murdoch   Professor Ameritus Carleton University,                                                                                                                   
       Brian Ripley     Professor of Statistics at the University of Auckland                                                                                                     
                                                                                                                                                                                  
       I suspect Python RandomForest is based on R RandomForest?                                                                                                                  
                                                                                                                                                                                  
       and many others                                                                                                                                                            
                                                                                                                                                                                  
       Method (R)                                                                                                                                                                 
                                                                                                                                                                                  
         1. Split the iris data into a training and hold out sample,                                                                                                              
            70% training and 30% holdout .                                                                                                                                        
            We will build the random forest model using the training data and                                                                                                     
            then apply the model to the hold out sample(verification data).                                                                                                       
                                                                                                                                                                                  
         2. 100 decision trees will be generated. We will pick with binary splits.                                                                                                
            Select randomly 2 of the four IRIS variable.                                                                                                                          
            see https://towardsdatascience.com/what-is-out-of-bag-oob-score-in-random-forest-a7fa23d710                                                                           
                                                                                                                                                                                  
         3. Do over trees                                                                                                                                                         
            Generate a bootstrap sample from the training data                                                                                                                    
            create a classification tree usin the bootstrapped data                                                                                                               
            for each split selecte 2 variables at random                                                                                                                          
            pick the best variable of the two and split then node                                                                                                                 
            use defualt stopping criteria                                                                                                                                         
            repeat                                                                                                                                                                
         4. Validate by applying the model developed using the training data to                                                                                                   
            the hold out sample                                                                                                                                                   
                                                                                                                                                                                  
                 _               _                                                                                                                                                
      ___  _   _| |_ _ __  _   _| |_                                                                                                                                              
     / _ \| | | | __| `_ \| | | | __|                                                                                                                                             
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                                                              
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                                                             
                    |_|                                                                                                                                                           
    FILE OUTPUTS                                                                                                                                                                  
                                                                                                                                                                                  
       https://tinyurl.com/ycgtmw2f  d:/pdf/gridplot.pdf       * Dimension reduction plot(like PCA?)                                                                              
       https://tinyurl.com/yc4jh86u  d:/pdf/mds.pdf            * Mutidemensional scaling - indication of good randomforest                                                        
       https://tinyurl.com/yaqublff  d:/txt/training.txt       * Summary randomforest training data output                                                                        
       https://tinyurl.com/ybfkklpg  d:/pdf/gini.pdf           * GINI plots                                                                                                       
       https://tinyurl.com/yaq4pjtf  d:/pdf/rocr.pdf           * ROC  -- true and false positive percents                                                                         
       https://tinyurl.com/y7rsoquz  d:/pdf/errorbytree.pdf    * Outof bag error by tree number                                                                                   
       https://tinyurl.com/y7e6cbrj  d:/txt/rf_classifier.txt  * Meta data on all possible R outputs;                                                                             
                                                                                                                                                                                  
    SAS dataset output                                                                                                                                                            
                                                                                                                                                                                  
       PREDICTED           Predictions using the holdout sample 47 obs                                                                                                            
       MISS_CLASSIFIED     Miss-classified observations using the holdout sample 47 obs                                                                                           
       GINI                GINI equality indexes by flower petals and sepals                                                                                                      
       OOB_ERRORS          Out of Bag errors by each of the 100 trees                                                                                                             
       ROCAUC              Area under the ROC curves by Species                                                                                                                   
       SASCODE             Deriving the sas code for tree number one and executing it                                                                                             
                                                                                                                                                                                  
    These outputs provide insight usin just one tree. Not really useful, except for understanding.                                                                                
    R 'averages' all 100 trees. More useful with other models like CART and regression.                                                                                           
                                                                                                                                                                                  
       Also on github                                                                                                                                                             
                                                                                                                                                                                  
       d:/txt/gettree.txt        * Extract dataa on one of the hundred trees - useful to create a decision tree                                                                   
       d:/txt/codesas.txt        * R code for running just one tree more useful for other models regression, cart..                                                               
       d:/txt/sascode.txt        * SAS code for running just one ecision tree                                                                                                     
       d:/txt/sqlcode.txt        * MySQL code                                                                                                                                     
       d:/pdf/decisiontree.pdf   * Plot of decistion tree (a little abreviated - not useful except for understanding)                                                             
         _             _                                                                                                                                                          
     ___| |_ __ _ _ __| |_                                                                                                                                                        
    / __| __/ _` | `__| __|                                                                                                                                                       
    \__ \ || (_| | |  | |_                                                                                                                                                        
    |___/\__\__,_|_|   \__|                                                                                                                                                       
     _                   _                                                                                                                                                        
    (_)_ __  _ __  _   _| |_                                                                                                                                                      
    | | `_ \| `_ \| | | | __|                                                                                                                                                     
    | | | | | |_) | |_| | |_                                                                                                                                                      
    |_|_| |_| .__/ \__,_|\__|                                                                                                                                                     
            |_|                                                                                                                                                                   
    */                                                                                                                                                                            
                                                                                                                                                                                  
    * IRIS DATA;                                                                                                                                                                  
                                                                                                                                                                                  
    libname xpt clear;                                                                                                                                                            
                                                                                                                                                                                  
    %utlfkil(d:/pdf/gridplot.pdf);                                                                                                                                                
    %utlfkil(d:/pdf/mds.pdf);                                                                                                                                                     
    %utlfkil(d:/xpt/want.xpt);                                                                                                                                                    
                                                                                                                                                                                  
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    options validvarname=v7;                                                                                                                                                      
                                                                                                                                                                                  
    libname sd1 "d:/sd1";                                                                                                                                                         
                                                                                                                                                                                  
    data sd1.have(rename=species=Species);                                                                                                                                        
       /* structure the SAS iris data to look like the R iris data */                                                                                                             
       retain sepallength sepalwidth petallength petalwidth Species;                                                                                                              
       set sashelp.iris;                                                                                                                                                          
       array ns[*] _numeric_;                                                                                                                                                     
       do i=1 to dim(ns);                                                                                                                                                         
         ns[i]=ns[i]/10;                                                                                                                                                          
       end;                                                                                                                                                                       
       drop i;                                                                                                                                                                    
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    /*                                                                                                                                                                            
      SD1.HAVE total obs=150                                                                                                                                                      
                                                                                                                                                                                  
     species   sepallength    sepalwidth    petallength    petalwidth                                                                                                             
                                                                                                                                                                                  
     Setosa        5.0            3.3           1.4            0.2                                                                                                                
     Setosa        4.6            3.4           1.4            0.3                                                                                                                
     Setosa        4.6            3.6           1.0            0.2                                                                                                                
     Setosa        5.1            3.3           1.7            0.5                                                                                                                
     Setosa        5.5            3.5           1.3            0.2                                                                                                                
     Setosa        4.8            3.1           1.6            0.2                                                                                                                
     Setosa        5.2            3.4           1.4            0.2                                                                                                                
     Setosa        4.9            3.6           1.4            0.1                                                                                                                
     Setosa        4.4            3.2           1.3            0.2                                                                                                                
     Setosa        5.0            3.5           1.6            0.6                                                                                                                
       ....                                                                                                                                                                       
                _     _         _       _                                                                                                                                         
      __ _ _ __(_) __| |  _ __ | | ___ | |_                                                                                                                                       
     / _` | `__| |/ _` | | `_ \| |/ _ \| __|                                                                                                                                      
    | (_| | |  | | (_| | | |_) | | (_) | |_                                                                                                                                       
     \__, |_|  |_|\__,_| | .__/|_|\___/ \__|                                                                                                                                      
     |___/               |_|                                                                                                                                                      
                                                                                                                                                                                  
    */                                                                                                                                                                            
                                                                                                                                                                                  
    options orientation=landscape;                                                                                                                                                
    ods graphics on / reset width=10in height=8in;                                                                                                                                
    ODS pdf file="d:/pdf/gridplot.pdf";                                                                                                                                           
                                                                                                                                                                                  
    title1 "Sepal and Petal Sizes in Iris Species";                                                                                                                               
    proc sgscatter data=sashelp.iris;                                                                                                                                             
    matrix sepalwidth sepallength petalwidth                                                                                                                                      
    petallength / group=species                                                                                                                                                   
    diagonal=(histogram kernel);                                                                                                                                                  
    run;                                                                                                                                                                          
    ods pdf close;                                                                                                                                                                
    ods graphics off;                                                                                                                                                             
                                                                                                                                                                                  
    /*                                                                                                                                                                            
       SPECIES                                                                                                                                                                    
                                                                                                                                                                                  
       + Setosa                                                                                                                                                                   
       . Versicolor                                                                                                                                                               
       X Virginica                                                                                                                                                                
                                                                                                                                                                                  
                  Sepal Width                Sepal Length                Petal Width                                                                                              
      S   ------------------------------------------------------- ---------------------------                                                                                     
      e  |             ##            ||                          ||                          |                                                                                    
      p  |             ##            ||                          ||                          |                                                                                    
      a  |             ##            ||           + +            ||           + +            |                                                                                    
      l  |          ## ##            ||        + +   +           ||        + +   +           |                                                                                    
         |          ## ##            ||  +  +++++++ +         x  ||  +  +++++++ +         x  |  ...                                                                               
      W  |          ## ## ##         ||+ +++ +++ +    .. xxx. x  ||+ +++ +++ +    .. xxx. x  |                                                                                    
      i  |          ## ## ##         ||+ + +++   . .. x..xxx xxx ||+ + +++   . .. x..xxx xxx |                                                                                    
      d  |       ## ## ## ## ##      ||     x ..  .x.x .xx.     x||     x ..  .x.x .xx.     x|                                                                                    
      t  |       ## ## ## ## ##      || +   ..    .    .         || +   ..    .    .         |                                                                                    
      h  |    ## ## ## ## ## ## ##   ||      .                   ||      .                   |                                                                                    
         ------------------------------------------------------------------------------------                                                                                     
      S  |                           |||                         ||                                                                                                               
      e  |                           |||                         ||                                                                                                               
      p  |                           |||       ##                ||                                                                                                               
      a  |  +   +                    |||       ## ## ##          ||                                                                                                               
      l  |+ +   +                    |||       ## ## ##          ||                             ...                                                                               
         |+ + + +                   x|||       ## ## ## ##       ||      ...                                                                                                      
      L  |  + + + +         . . .   .|||       ## ## ## ##       ||                                                                                                               
      e  |+ + +      . . . . x . x  x|||       #### ## ## ##     ||                                                                                                               
      n  |     . . . . x x . x x x xx|||       ## ## ## ## ##    ||                                                                                                               
      g  |  +  . .   .   .           |||    ## ## ## ## ## ## ## ||                                                                                                               
      t   ---------------------------------------------------------                                                                                                               
      h                                                                                                                                                                           
               ...                               ...                     ...                    ...                                                                               
                   _             _       _                                                                                                                                        
     _ __ ___   __| |___   _ __ | | ___ | |_                                                                                                                                      
    | `_ ` _ \ / _` / __| | `_ \| |/ _ \| __|                                                                                                                                     
    | | | | | | (_| \__ \ | |_) | | (_) | |_                                                                                                                                      
    |_| |_| |_|\__,_|___/ | .__/|_|\___/ \__|                                                                                                                                     
                          |_|                                                                                                                                                     
                                                                                                                                                                                  
    https://tinyurl.com/yc4jh86u                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset/blob/master/mds.pdf                                                   
    */                                                                                                                                                                            
                                                                                                                                                                                  
                                                                                                                                                                                  
    proc datasets lib=work nolist;                                                                                                                                                
     delete want_mds;                                                                                                                                                             
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    %utl_submit_r64('                                                                                                                                                             
    library(haven);                                                                                                                                                               
    library(SASxport);                                                                                                                                                            
    library(data.table);                                                                                                                                                          
    iris<-read_sas("d:/sd1/have.sas7bdat");                                                                                                                                       
    iris$Species<-as.factor(iris$Species);                                                                                                                                        
    irisDist <- dist(iris[,1:4]);                                                                                                                                                 
    irisMds = cmdscale(irisDist, k=2);                                                                                                                                            
    str(irisMds);                                                                                                                                                                 
    pdf(file="d:/pdf/mds.pdf");                                                                                                                                                   
    plot(irisMds);                                                                                                                                                                
    text(irisMds[,1], (irisMds[,2]+max(irisMds[,2])*0.05), labels=1:nrow(irisMds), cex = 0.4, xpd = TRUE);                                                                        
    points(irisMds, col=c("red", "green", "blue")[as.numeric(iris$Species)]);                                                                                                     
    pdf();                                                                                                                                                                        
    want<-as.data.table(irisMds);                                                                                                                                                 
    write.xport(want,file="d:/xpt/want.xpt");                                                                                                                                     
    ');                                                                                                                                                                           
                                                                                                                                                                                  
    /*                                                                                                                                                                            
    libname xpt xport "d:/xpt/want.xpt";                                                                                                                                          
    data want_mds;                                                                                                                                                                
      retain species;                                                                                                                                                             
      merge xpt.want sashelp.iris(keep=species);                                                                                                                                  
      select (species);                                                                                                                                                           
         when ("Setosa"    ) sym=  "+";                                                                                                                                           
         when ("Versicolor") sym=  ".";                                                                                                                                           
         when ("Virginica" ) sym=  "X";                                                                                                                                           
      end;                                                                                                                                                                        
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    libname xpt clear;                                                                                                                                                            
                                                                                                                                                                                  
    options ls=64 ps=32;                                                                                                                                                          
    proc plot data=want(rename=v2=v12345678901234567890);                                                                                                                         
     plot v12345678901234567890*v1=" " $ sym /box;                                                                                                                                
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
                                                                                                                                                                                  
    Dimension reduction using Multi-dimensional Scalinig                                                                                                                          
    IS related to distances between poitns in 4 dimenional space,                                                                                                                 
                                                                                                                                                                                  
    Give us an ideaif the Random forest will be sucessful?                                                                                                                        
                                                                                                                                                                                  
                                                                                                                                                                                  
           -5.0     -2.5      0.0      2.5      5.0                                                                                                                               
         2 +-+--------+--------+--------+--------+--+ 2                                                                                                                           
           |                                        |                                                                                                                             
           |          +    + Setosa        X        |                                                                                                                             
      D    |         +     . Versicolor     X       |                                                                                                                             
      I  1 +          +    X Virginica              + 1                                                                                                                           
      M    |         +++                  X         |                                                                                                                             
      _    |          +             .   X XX        |                                                                                                                             
      2    |         +++          ..  XXXXX X       |                                                                                                                             
           |       + ++           ....XXX    X      |                                                                                                                             
         0 +         +++        .... XXXX           + 0                                                                                                                           
           |         ++       . ....XXXX            |                                                                                                                             
           |        ++        ..... XX              |                                                                                                                             
           |       + +        .....XXX              |                                                                                                                             
           |                .  ..   X               |                                                                                                                             
        -1 +         +      .                       + 1                                                                                                                           
           |                 .   X                  |                                                                                                                             
           |                                        |                                                                                                                             
           +-+--------+--------+--------+--------+--+                                                                                                                             
           -5.0     -2.5      0.0      2.5      5.0                                                                                                                               
                                                                                                                                                                                  
                            Dim_1                                                                                                                                                 
                                                                                                                                                                                  
    WORK.WANT_MDS TOTAL OBS=150                                                                                                                                                   
                                                                                                                                                                                  
      SPECIES       V1          V2       SYM                                                                                                                                      
                                                                                                                                                                                  
      Setosa     -2.70336     0.10771     +                                                                                                                                       
      Setosa     -2.82054    -0.08946     +                                                                                                                                       
      Setosa     -3.21594     0.13347     +                                                                                                                                       
      Setosa     -2.30273     0.09871     +                                                                                                                                       
      Setosa     -2.62524     0.59937     +                                                                                                                                       
      Setosa     -2.58740    -0.20432     +                                                                                                                                       
     ...                                                                                                                                                                          
                         _                  __                     _                                                                                                              
     _ __ __ _ _ __   __| | ___  _ __ ___  / _| ___  _ __ ___  ___| |_                                                                                                            
    | `__/ _` | `_ \ / _` |/ _ \| `_ ` _ \| |_ / _ \| `__/ _ \/ __| __|                                                                                                           
    | | | (_| | | | | (_| | (_) | | | | | |  _| (_) | | |  __/\__ \ |_                                                                                                            
    |_|  \__,_|_| |_|\__,_|\___/|_| |_| |_|_|  \___/|_|  \___||___/\__|                                                                                                           
                 _               _                                                                                                                                                
      ___  _   _| |_ _ __  _   _| |_                                                                                                                                              
     / _ \| | | | __| `_ \| | | | __|                                                                                                                                             
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                                                              
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                                                             
                    |_|                                                                                                                                                           
                                                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset/blob/master/rf_classifier.txt                                         
                                                                                                                                                                                  
                                                                                                                                                                                  
    THIS LIST CONTAINS THE META DATA ON ALL OF THE RANDOMFOREST OUTPUT                                                                                                            
    ===================================================================                                                                                                           
                                                                                                                                                                                  
    List of 19                                                                                                                                                                    
                                                                                                                                                                                  
     $ call           : language randomForest(formula = Species ~ ., data = training, ntree = 100, mtry = 2,      importance = TRUE)                                              
     $ type           : chr "classification"                                                                                                                                      
                                                                                                                                                                                  
    PREDICTION IN TRAINING SAMPLE (103 OBSERVATION - TRAINING SET                                                                                                                 
                                                                                                                                                                                  
     $ predicted      : Factor w/ 3 levels "Setosa","Versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...                                                                                      
      ..- attr(*, "names")= chr [1:103] "1" "2" "3" "4" ...                                                                                                                       
                                                                                                                                                                                  
    ERROR ASSOCIATED WITH EACH OF THE HUNDRED TRESS                                                                                                                               
                                                                                                                                                                                  
                                                                                                                                                                                  
     $ err.rate       : num [1:100, 1:4] 0.0513 0.0656 0.0658 0.0595 0.0761 ...                                                                                                   
      ..- attr(*, "dimnames")=List of 2                                                                                                                                           
      .. ..$ : NULL                                                                                                                                                               
      .. ..$ : chr [1:4] "OOB" "Setosa" "Versicolor" "Virginica"                                                                                                                  
                                                                                                                                                                                  
    MISS-CLASSIFICATION MATRIX IN THE SMALLER HOLD OUT SAMPLE - 47 OBSERVATIONS                                                                                                   
    ============================================================================                                                                                                  
                                                                                                                                                                                  
     $ confusion      : num [1:3, 1:4] 30 0 0 0 36 4 0 2 31 0 ...                                                                                                                 
      ..- attr(*, "dimnames")=List of 2                                                                                                                                           
      .. ..$ : chr [1:3] "Setosa" "Versicolor" "Virginica"                                                                                                                        
      .. ..$ : chr [1:4] "Setosa" "Versicolor" "Virginica" "class.error"                                                                                                          
     $ votes          : 'matrix' num [1:103, 1:3] 1 1 0.921 1 1 ...                                                                                                               
                                                                                                                                                                                  
      ..- attr(*, "dimnames")=List of 2                                                                                                                                           
      .. ..$ : chr [1:103] "1" "2" "3" "4" ...                                                                                                                                    
      .. ..$ : chr [1:3] "Setosa" "Versicolor" "Virginica"                                                                                                                        
     $ oob.times      : num [1:103] 38 37 38 37 29 37 44 42 31 30 ...                                                                                                             
     $ classes        : chr [1:3] "Setosa" "Versicolor" "Virginica"                                                                                                               
                                                                                                                                                                                  
    Mean Decrease Accuracy and GINI                                                                                                                                               
    ==============================                                                                                                                                                
                                                                                                                                                                                  
     $ importance     : num [1:4, 1:5] 0.0281 0.0143 0.3746 0.3098 0.0143 ...                                                                                                     
      ..- attr(*, "dimnames")=List of 2                                                                                                                                           
      .. ..$ : chr [1:4] "sepallength" "sepalwidth" "petallength" "petalwidth"                                                                                                    
      .. ..$ : chr [1:5] "Setosa" "Versicolor" "Virginica" "MeanDecreaseAccuracy" ...                                                                                             
     $ importanceSD   : num [1:4, 1:4] 0.0113 0.00637 0.03421 0.03418 0.00724 ...                                                                                                 
      ..- attr(*, "dimnames")=List of 2                                                                                                                                           
      .. ..$ : chr [1:4] "sepallength" "sepalwidth" "petallength" "petalwidth"                                                                                                    
      .. ..$ : chr [1:4] "Setosa" "Versicolor" "Virginica" "MeanDecreaseAccuracy"                                                                                                 
     $ localImportance: NULL                                                                                                                                                      
     $ proximity      : NULL                                                                                                                                                      
     $ ntree          : num 100                                                                                                                                                   
     $ mtry           : num 2                                                                                                                                                     
     $ forest         :List of 14                                                                                                                                                 
      ..$ ndbigtree : int [1:100] 17 9 15 11 15 21 13 17 17 7 ...                                                                                                                 
      ..$ nodestatus: int [1:31, 1:100] 1 1 1 1 1 -1 1 -1 1 1 ...                                                                                                                 
      ..$ bestvar   : int [1:31, 1:100] 2 4 3 3 1 0 1 0 3 2 ...                                                                                                                   
      ..$ treemap   : int [1:31, 1:2, 1:100] 2 4 6 8 10 0 12 0 14 16 ...                                                                                                          
      ..$ nodepred  : int [1:31, 1:100] 0 0 0 0 0 1 0 1 0 0 ...                                                                                                                   
                                                                                                                                                                                  
    SPLIT POINTS                                                                                                                                                                  
    ============                                                                                                                                                                  
      ..$ xbestsplit: num [1:31, 1:100] 3.25 1.65 3.1 2.3 5.95 0 6.1 0 5.45 3 ...                                                                                                 
      ..$ pid       : num [1:3] 1 1 1                                                                                                                                             
      ..$ cutoff    : num [1:3] 0.333 0.333 0.333                                                                                                                                 
      ..$ ncat      : Named int [1:4] 1 1 1 1                                                                                                                                     
      .. ..- attr(*, "names")= chr [1:4] "sepallength" "sepalwidth" "petallength" "petalwidth"                                                                                    
      ..$ maxcat    : int 1                                                                                                                                                       
      ..$ nrnodes   : int 31                                                                                                                                                      
      ..$ ntree     : num 100                                                                                                                                                     
      ..$ nclass    : int 3                                                                                                                                                       
      ..$ xlevels   :List of 4                                                                                                                                                    
      .. ..$ sepallength: num 0                                                                                                                                                   
      .. ..$ sepalwidth : num 0                                                                                                                                                   
      .. ..$ petallength: num 0                                                                                                                                                   
      .. ..$ petalwidth : num 0                                                                                                                                                   
     $ y              : Factor w/ 3 levels "Setosa","Versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...                                                                                      
      ..- attr(*, "names")= chr [1:103] "1" "2" "3" "4" ...                                                                                                                       
     $ test           : NULL                                                                                                                                                      
     $ inbag          : NULL                                                                                                                                                      
     $ terms          :Classes 'terms', 'formula'  language Species ~ sepallength + sepalwidth + petallength + petalwidth                                                         
      .. ..- attr(*, "variables")= language list(Species, sepallength, sepalwidth, petallength, petalwidth)                                                                       
      .. ..- attr(*, "factors")= int [1:5, 1:4] 0 1 0 0 0 0 0 1 0 0 ...                                                                                                           
      .. .. ..- attr(*, "dimnames")=List of 2                                                                                                                                     
      .. .. .. ..$ : chr [1:5] "Species" "sepallength" "sepalwidth" "petallength" ...                                                                                             
      .. .. .. ..$ : chr [1:4] "sepallength" "sepalwidth" "petallength" "petalwidth"                                                                                              
      .. ..- attr(*, "term.labels")= chr [1:4] "sepallength" "sepalwidth" "petallength" "petalwidth"                                                                              
      .. ..- attr(*, "order")= int [1:4] 1 1 1 1                                                                                                                                  
      .. ..- attr(*, "intercept")= num 0                                                                                                                                          
      .. ..- attr(*, "response")= int 1                                                                                                                                           
      .. ..- attr(*, ".Environment")=<environment: R_GlobalEnv>                                                                                                                   
      .. ..- attr(*, "predvars")= language list(Species, sepallength, sepalwidth, petallength, petalwidth)                                                                        
      .. ..- attr(*, "dataClasses")= Named chr [1:5] "factor" "numeric" "numeric" "numeric" ...                                                                                   
      .. .. ..- attr(*, "names")= chr [1:5] "Species" "sepallength" "sepalwidth" "petallength" ...                                                                                
     - attr(*, "class")= chr [1:2] "randomForest.formula" "randomForest"                                                                                                          
                          _      _                                                                                                                                                
     _ __  _ __ ___  __| (_)  __| |_                                                                                                                                              
    | `_ \| `__/ _ \/ _` | |/ __| __|                                                                                                                                             
    | |_) | | |  __/ (_| | | (__| |_                                                                                                                                              
    | .__/|_|  \___|\__,_|_|\___|\__|                                                                                                                                             
    |_|                                                                                                                                                                           
                                                                                                                                                                                  
                                                                                                                                                                                  
    TRAINING SAMPLE                                                                                                                                                               
    ===============                                                                                                                                                               
                                                                                                                                                                                  
    * Applying the model based on the training sample to the hold out sample 47 Observations                                                                                      
                                                                                                                                                                                  
    WORK.WANT_R total obs=47                                                                                                                                                      
                                                                                                                                                                                  
     SPECIES       PREDICTION    SEPALLENGTH    SEPALWIDTH    PETALLENGTH    PETALWIDTH                                                                                           
                                                                                                                                                                                  
     Setosa        Setosa            4.6            3.4           1.4            0.3                                                                                              
     Setosa        Setosa            5.1            3.3           1.7            0.5                                                                                              
     Setosa        Setosa            4.4            3.2           1.3            0.2                                                                                              
     Setosa        Setosa            4.8            3.0           1.4            0.3                                                                                              
     Setosa        Setosa            5.1            3.8           1.6            0.2                                                                                              
     Setosa        Setosa            4.8            3.4           1.9            0.2                                                                                              
     Setosa        Setosa            5.0            3.0           1.6            0.2                                                                                              
    ...                                                                                                                                                                           
                                                                                                                                                                                  
                                                                                                                                                                                  
     _             _       _                                    _      _                                                                                                          
    | |_ _ __ __ _(_)_ __ (_)_ __   __ _   _ __  _ __ ___  __| (_)  __| |_                                                                                                        
    | __| `__/ _` | | `_ \| | `_ \ / _` | | `_ \| `__/ _ \/ _` | |/ __| __|                                                                                                       
    | |_| | | (_| | | | | | | | | | (_| | | |_) | | |  __/ (_| | | (__| |_                                                                                                        
     \__|_|  \__,_|_|_| |_|_|_| |_|\__, | | .__/|_|  \___|\__,_|_|\___|\__|                                                                                                       
                                   |___/  |_|                                                                                                                                     
                                                                                                                                                                                  
                                                                                                                                                                                  
    Training- The model is built with 70% of the iris data ~.7*150 = 103                                                                                                          
                                                                                                                                                                                  
    https://tinyurl.com/yaqublff                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset/blob/master/training.txt                                              
                                                                                                                                                                                  
    Call:                                                                                                                                                                         
     randomForest(formula = Species ~ ., data = training,                                                                                                                         
                   ntree = 100,      mtry = 2, importance = TRUE)                                                                                                                 
                                                                                                                                                                                  
                   Type of random forest: classification                                                                                                                          
                         Number of trees: 100                                                                                                                                     
                                                                                                                                                                                  
    No. of variables tried at each split: 2                                                                                                                                       
                                                                                                                                                                                  
            OOB estimate of  error rate: 5.83%  (6/103)                                                                                                                           
                                                                                                                                                                                  
    Training Prediction matrix:                                                                                                                                                   
                                                                                                                                                                                  
               Setosa   Versicolor   Virginica    Sum        class.error                                                                                                          
                                                                                                                                                                                  
    Setosa         30            0           0    30         0.00000000                                                                                                           
    Versicolor      0           36           2    38   2/38  0.05263158  * 2 miss-classification                                                                                  
    Virginica       0            4          31    35   4/35  0.11428571  * 4 miss-classification                                                                                  
                                                                                                                                                                                  
    Total          30           40          33   103                                                                                                                              
                                                                                                                                                                                  
     _           _     _               _                               _                                                                                                          
    | |__   ___ | | __| |   ___  _   _| |_   ___  __ _ _ __ ___  _ __ | | ___                                                                                                     
    | `_ \ / _ \| |/ _` |  / _ \| | | | __| / __|/ _` | `_ ` _ \| `_ \| |/ _ \                                                                                                    
    | | | | (_) | | (_| | | (_) | |_| | |_  \__ \ (_| | | | | | | |_) | |  __/                                                                                                    
    |_| |_|\___/|_|\__,_|  \___/ \__,_|\__| |___/\__,_|_| |_| |_| .__/|_|\___|                                                                                                    
                                                                |_|                                                                                                               
                                                                                                                                                                                  
                                                                                                                                                                                  
    * This sample was not used in the derivation of the model.                                                                                                                    
      It is the independent hold out sample used for verification of the model.                                                                                                   
                                                                                                                                                                                  
    The claasification matrix is the result od using the ensemble of trees and                                                                                                    
    not one best tree.                                                                                                                                                            
                                                                                                                                                                                  
    WORK.WANTXPO total obs=4   ~.30*150=45 (hold out or test data)                                                                                                                
                                                                                                                                                                                  
    LEVELS        Setosa    Versicolor    Virginica    Sum                                                                                                                        
                                                                                                                                                                                  
    Setosa          20           0             0        20                                                                                                                        
    Versicolor       0          11             1**      12  1 out of 12 miss-classified                                                                                           
    Virginica        0           1**          14        15  1 out of 14 miss-classified                                                                                           
                                                                                                                                                                                  
    Sum             20          12            15        47                                                                                                                        
                                                                                                                                                                                  
    Table of SPECIES by PREDICTION                                                                                                                                                
                                                                                                                                                                                  
    SPECIES(Species)                                                                                                                                                              
                PREDICTION(prediction_for_table)                                                                                                                                  
                                                                                                                                                                                  
    Frequency  |                                                                                                                                                                  
    Percent    |                                                                                                                                                                  
    Row Pct    |                                                                                                                                                                  
    Col Pct    |Setosa  |Versicol|Virginic|  Total                                                                                                                                
               |        |or      |a       |                                                                                                                                       
    -----------+--------+--------+--------+                                                                                                                                       
    Setosa     |     20 |      0 |      0 |     20                                                                                                                                
               |  42.55 |   0.00 |   0.00 |  42.55                                                                                                                                
               | 100.00 |   0.00 |   0.00 |                                                                                                                                       
               | 100.00 |   0.00 |   0.00 |                                                                                                                                       
    -----------+--------+--------+--------+                                                                                                                                       
    Versicolor |      0 |     11 |      1 |     12                                                                                                                                
               |   0.00 |  23.40 |   2.13 |  25.53                                                                                                                                
               |   0.00 |  91.67 |   8.33 |                                                                                                                                       
               |   0.00 |  91.67 |   6.67 |                                                                                                                                       
    -----------+--------+--------+--------+                                                                                                                                       
    Virginica  |      0 |      1 |     14 |     15                                                                                                                                
               |   0.00 |   2.13 |  29.79 |  31.91                                                                                                                                
               |   0.00 |   6.67 |  93.33 |                                                                                                                                       
               |   0.00 |   8.33 |  93.33 |                                                                                                                                       
    -----------+--------+--------+--------+                                                                                                                                       
    Total            20       12       15       47                                                                                                                                
                  42.55    25.53    31.91   100.00                                                                                                                                
                                                                                                                                                                                  
                                                                                                                                                                                  
     _ __ ___   ___    __ _ _ __ ___  __ _ ___                                                                                                                                    
    | `__/ _ \ / __|  / _` | `__/ _ \/ _` / __|                                                                                                                                   
    | | | (_) | (__  | (_| | | |  __/ (_| \__ \                                                                                                                                   
    |_|  \___/ \___|  \__,_|_|  \___|\__,_|___/                                                                                                                                   
                                                                                                                                                                                  
                                                                                                                                                                                  
                                                                                                                                                                                  
    Receiver Operating Characteristic (ROC) curve                                                                                                                                 
    https://tinyurl.com/yaq4pjtf                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset/blob/master/rocr.pdf                                                  
                                                                                                                                                                                  
    WORK.WANT_AUC total obs=1                                                                                                                                                     
                                                                                                                                                                                  
     SETOSA    VERSICOL    VIRGINIC                                                                                                                                               
                                                                                                                                                                                  
        1       0.99762     0.99792                                                                                                                                               
                                                                                                                                                                                  
                               ROC CURVES                                                                                                                                         
                                                                                                                                                                                  
                                                                                                                                                                                  
                0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0                                                                                                                       
               --+---+---+---+---+---+---+---+---+---+---+--                                                                                                                      
               | |   |<|-1/15 Virginica (AUC=0.99792)      |                                                                                                                      
       t   1.0 + |___| |                                   + 1.0                                                                                                                  
       r       | |_____|<-1/12 Versicolor (AUC=0.99762)    |                                                                                                                      
       u   0.9 + |                                         + 0.9                                                                                                                  
       e       | |                                         |                                                                                                                      
       -   0.8 + |<-Setosa no false positives              + 0.8                                                                                                                  
       p       | |  Perfect classification                 |                                                                                                                      
       o   0.7 + |  All true positives                     + 0.7                                                                                                                  
       s       | |  AUC=1                                  |                                                                                                                      
       i   0.6 + |                                         + 0.6                                                                                                                  
       t       | |                                         |                                                                                                                      
       i   0.5 + |                                         + 0.5                                                                                                                  
       v       | |                                         |                                                                                                                      
       e   0.4 + |                                         + 0.4                                                                                                                  
       -       | |                                         |                                                                                                                      
       r   0.3 + |                                         + 0.3                                                                                                                  
       a       | |                                         |                                                                                                                      
       t   0.2 + |                                         + 0.2                                                                                                                  
       e       | |                                         |                                                                                                                      
           0.1 + |                                         + 0.1                                                                                                                  
               | |                                         |                                                                                                                      
           0.0 + |                                         + 0.0                                                                                                                  
               | |                                         |                                                                                                                      
               ---+---+---+---+---+---+---+---+---+---+---+--                                                                                                                     
               0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1.0                                                                                                                        
                                                                                                                                                                                  
                           false_positive_rate                                                                                                                                    
                                                                                                                                                                                  
               _                    _               _  __ _          _                                                                                                            
     _ __ ___ (_)___ ___        ___| | __ _ ___ ___(_)/ _(_) ___  __| |                                                                                                           
    | `_ ` _ \| / __/ __|_____ / __| |/ _` / __/ __| | |_| |/ _ \/ _` |                                                                                                           
    | | | | | | \__ \__ \_____| (__| | (_| \__ \__ \ |  _| |  __/ (_| |                                                                                                           
    |_| |_| |_|_|___/___/      \___|_|\__,_|___/___/_|_| |_|\___|\__,_|                                                                                                           
                                                                                                                                                                                  
                                                                                                                                                                                  
                                                                                                                                                                                  
    WORK.WANTXPO total obs=4   ~.30*150=45 (hold out o                                                                                                                            
                                                                                                                                                                                  
    LEVELS        Setosa    Versicolor    Virginica                                                                                                                               
                                                                                                                                                                                  
    Setosa          20           0             0                                                                                                                                  
    Versicolor       0          11            1*b                                                                                                                                 
    Virginica        0          1*a           14                                                                                                                                  
                                                                                                                                                                                  
                                                                                                                                                                                  
    SAS Table                                                                                                                                                                     
    WORK.MISS_CLASSIFIED total obs=2                                                                                                                                              
                                                                                                                                                                                  
      species      prediction    sepallength    sepalwidth    petallength    petalwidth                                                                                           
                                                                                                                                                                                  
     Versicolor    Virginica  *b     6.7            3.0           5.0            1.7                                                                                              
     Virginica     Versicolor *a     6.3            2.8           5.1            1.5                                                                                              
                                                                                                                                                                                  
           _       _                                                                                                                                                              
      __ _(_)_ __ (_)                                                                                                                                                             
     / _` | | `_ \| |                                                                                                                                                             
    | (_| | | | | | |                                                                                                                                                             
     \__, |_|_| |_|_|                                                                                                                                                             
     |___/                                                                                                                                                                        
                                                                                                                                                                                  
                                                                                                                                                                                  
    * GINI is a measure of equality for the iris values;                                                                                                                          
    * Decrease in gini measuse the usbulnees of subsequent value to minimize dispersion?                                                                                          
    * useful for selecting variables;                                                                                                                                             
                                                                                                                                                                                  
    WANT_IMPORTANCE total obs=4                                                                                                                                                   
                                                                                                                                                                                  
                                                Mean     Mean                                                                                                                     
                                              Decrease Decrease                                                                                                                   
         V1       Setosa Versicolor Virginica Accuracy   Gini                                                                                                                     
                                                                                                                                                                                  
     sepallength  2.4882    1.9798    2.6310    3.6991   5.9373                                                                                                                   
     sepalwidth   2.2414   -0.9127    1.3206    1.6003   2.9122                                                                                                                   
     petallength 10.9504   14.1629   11.7152   15.8271  28.9883                                                                                                                   
     petalwidth   9.0622   12.6714   14.8953   15.5061  29.8110                                                                                                                   
                                                                                                                                                                                  
    data sym;                                                                                                                                                                     
      set want_importance ;                                                                                                                                                       
      symgin=put(round(MEANDECREASEGINI,1),2.);                                                                                                                                   
      symacc=put(round(MEANDECREASEACCURACY,1),2.);                                                                                                                               
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    options ls=64 ps=18;                                                                                                                                                          
    proc plot data=sym;                                                                                                                                                           
    plot v1*MeanDecreaseAccuracy="*" $ symacc /box                                                                                                                                
      vaxis="sepalwidth" "sepallength" "petallength" "petalwidth";                                                                                                                
    plot v1*MEANDECREASEGINI="*" $ symgin /box                                                                                                                                    
      vaxis="sepalwidth" "sepallength" "petallength" "petalwidth";                                                                                                                
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
       GINI is a measure of the equality of values.                                                                                                                               
       The lower the Gini the more equal the values are.                                                                                                                          
                                                                                                                                                                                  
                                                                                                                                                                                  
                    0          10    20          30                                                                                                                               
                 ---+-----------+-///-+-----------+---                                                                                                                            
                 |                                   |                                                                                                                            
     petalwidth  +                             30 *  + petalwidth                                                                                                                 
                 |                                   |                                                                                                                            
                 |                                   |                                                                                                                            
     petallength +                               * 29+ petallength                                                                                                                
                 |                                   |                                                                                                                            
                 |                                   |                                                                                                                            
     sepallength +         *  6                      + sepallength                                                                                                                
                 |                                   |                                                                                                                            
                 |                                   |                                                                                                                            
     sepalwidth  +     *  3                          + sepalwidth                                                                                                                 
                 ---+-----------+-///-+-----------+---                                                                                                                            
                    0          10    20          30                                                                                                                               
                                                                                                                                                                                  
                             MeanDecreaseGini                                                                                                                                     
                                                                                                                                                                                  
                                                                                                                                                                                  
                                                                                                                                                                                  
                 --+----------+---///--+----------+---                                                                                                                            
                 |                                   |                                                                                                                            
     petalwidth  +                      * 16         + petalwidth                                                                                                                 
                 |                                   |                                                                                                                            
                 |                                   |                                                                                                                            
     petallength +                       * 16        + petallength                                                                                                                
                 |                                   |                                                                                                                            
                 |                                   |                                                                                                                            
     sepallength +         *  4                      + sepallength                                                                                                                
                 |                                   |                                                                                                                            
                 |                                   |                                                                                                                            
     sepalwidth  +     *  2                          + sepalwidth                                                                                                                 
                 --+----------+---///--+----------+---                                                                                                                            
                   0          5       15         20                                                                                                                               
                                                                                                                                                                                  
                          MeanDecreaseAccuracy                                                                                                                                    
                                                                                                                                                                                  
                _   _                                                                                                                                                             
      __ _  ___| |_| |_ _ __ ___  ___                                                                                                                                             
     / _` |/ _ \ __| __| `__/ _ \/ _ \                                                                                                                                            
    | (_| |  __/ |_| |_| | |  __/  __/                                                                                                                                            
     \__, |\___|\__|\__|_|  \___|\___|                                                                                                                                            
     |___/                                                                                                                                                                        
      __ _          _     ____  ____    _                                                                                                                                         
     / _(_)_ __ ___| |_  |___ \| ___|  | |_ _ __ ___  ___  ___                                                                                                                    
    | |_| | `__/ __| __|   __) |___ \  | __| `__/ _ \/ _ \/ __|                                                                                                                   
    |  _| | |  \__ \ |_   / __/ ___) | | |_| | |  __/  __/\__ \                                                                                                                   
    |_| |_|_|  |___/\__| |_____|____/   \__|_|  \___|\___||___/                                                                                                                   
                                                                                                                                                                                  
                                                                                                                                                                                  
                                                                                                                                                                                  
    You cant pick out one tree but random forest 'averages'                                                                                                                       
    many trees to classify observations                                                                                                                                           
                                                                                                                                                                                  
    Up to 40 obs WORK.WANT_ERR total obs=100                                                                                                                                      
                                                                                                                                                                                  
              OUT OF                                                                                                                                                              
            BAG ERROR                                                                                                                                                             
     TREE      OOB      SETOSA    VERSICOL    VIRGINIC                                                                                                                            
                                                                                                                                                                                  
       1     0.05128       0       0.07143     0.07143                                                                                                                            
       2     0.06557       0       0.09524     0.09524                                                                                                                            
       3     0.06579       0       0.10000     0.07692                                                                                                                            
       4     0.05952       0       0.06452     0.10345                                                                                                                            
       5     0.07609       0       0.12121     0.09677                                                                                                                            
       6     0.06250       0       0.08824     0.09091                                                                                                                            
       7     0.10204       0       0.17143     0.11765                                                                                                                            
     ....                                                                                                                                                                         
                                                                                                                                                                                  
    * Althoug it is not appropriate to look at one tree,                                                                                                                          
      beause a single tree will not be an improvement over                                                                                                                        
      simple methods like CART.                                                                                                                                                   
      Random forest `averages` many trees.                                                                                                                                        
                                                                                                                                                                                  
    Lets look at the Out of Bag Error versus tree number.                                                                                                                         
                                                                                                                                                                                  
                                                                                                                                                                                  
        OOB  0  2  4  6  8 10 12 14 16 18 20 22 24                                                                                                                                
            -+--+--+--+--+--+--+--+--+--+--+--+--+--                                                                                                                              
            |                     |                |                                                                                                                              
       0.12 +                     |                + 0.12                                                                                                                         
            |                     |                |                                                                                                                              
            |                     | Tree 14        |                                                                                                                              
            |                     | has least error|                                                                                                                              
       0.10 +           **        | of first 25    + 0.10                                                                                                                         
            |                     |                |                                                                                                                              
            |                     |                |                                                                                                                              
            |                     |                |                                                                                                                              
       0.08 +                     |                + 0.08                                                                                                                         
            |        *            |                |                                                                                                                              
            |              **     |                |                                                                                                                              
            |   * *   *           |                |                                                                                                                              
       0.06 +      *           * *| **    ** *     + 0.06                                                                                                                         
            |                     |                |                                                                                                                              
            |  *              *   |    **     * ** |                                                                                                                              
            |                     *                |                                                                                                                              
       0.04 +                     |                + 0.04                                                                                                                         
            |                     |                |                                                                                                                              
            -+--+--+--+--+--+--+--+--+--+--+--+--+--                                                                                                                              
             0  2  4  6  8 10 12 14 16 18 20 22 24                                                                                                                                
                                                                                                                                                                                  
                              TREE                                                                                                                                                
                                                                                                                                                                                  
           _       _     _                                                                                                                                                        
     _ __ | | ___ | |_  | |_ _ __ ___  ___                                                                                                                                        
    | `_ \| |/ _ \| __| | __| `__/ _ \/ _ \                                                                                                                                       
    | |_) | | (_) | |_  | |_| | |  __/  __/                                                                                                                                       
    | .__/|_|\___/ \__|  \__|_|  \___|\___|                                                                                                                                       
    |_|                                                                                                                                                                           
                                                                                                                                                                                  
                                                                                                                                                                                  
      This is not useful, it is just one of 100 trees.                                                                                                                            
      Just shown for academic reasons to present one of the ensemble of trees.                                                                                                    
      Random Forest `averages` the uncorrelated treees.                                                                                                                           
      Tndom selection and bootstrap ensures uncorreated trees.                                                                                                                    
                                                                                                                                                                                  
                                  sepalwidth                                                                                                                                      
                                                                                                                                                                                  
                                 <=3.25/\ > 3.21                                                                                                                                  
                                      /  \                                                                                                                                        
                                     /    \                                                                                                                                       
                                    /      \                                                                                                                                      
                                   /        \                                                                                                                                     
                                  /          \                                                                                                                                    
                                 /            \ petallength                                                                                                                       
                                /        <=3.1 * > 3.1                                                                                                                            
                               /              / \                                                                                                                                 
                              /              /   \                                                                                                                                
                  petallength/              /     \                                                                                                                               
                      <=1.65* >1.65     Setosa     \ sepallength                                                                                                                  
                           / \                 <=6.2\  >6.2                                                                                                                       
                          /   \                     /*                                                                                                                            
                         /     \                   /  \                                                                                                                           
                        /       \                 /    \                                                                                                                          
                       /         \               /      \                                                                                                                         
                      /           \       VERICOLOR   VIRGINICA                                                                                                                   
                     /             \                                                                                                                                              
                sepalength          \                                                                                                                                             
              <=2.3*\ >2.3           \                                                                                                                                            
                  /  \                \                                                                                                                                           
            SERTOSA   \                \                                                                                                                                          
                       \                \                                                                                                                                         
                    petalwidth           \                                                                                                                                        
                  <=5.45 *>5.45        petalwidth                                                                                                                                 
                        /\           <=5.95* >5.95                                                                                                                                
                       /  \               / \                                                                                                                                     
                      /    \             /   \                                                                                                                                    
                     /      \     sepallength \                                                                                                                                   
             VERSICOLOR  VIRGINICA   <=3*>3    \                                                                                                                                  
                                      / \    VIRGINICA                                                                                                                            
                                     /   \                                                                                                                                        
                                    /     \                                                                                                                                       
                              VIRGINICA  VERSICOLOR                                                                                                                               
                                                                                                                                                                                  
                                   _                                                                                                                                              
     ___  __ _ ___    ___ ___   __| | ___                                                                                                                                         
    / __|/ _` / __|  / __/ _ \ / _` |/ _ \                                                                                                                                        
    \__ \ (_| \__ \ | (_| (_) | (_| |  __/                                                                                                                                        
    |___/\__,_|___/  \___\___/ \__,_|\___|                                                                                                                                        
                                                                                                                                                                                  
                                                                                                                                                                                  
    SAS CODE                                                                                                                                                                      
    ========                                                                                                                                                                      
                                                                                                                                                                                  
    github SAS CODE                                                                                                                                                               
    https://tinyurl.com/y8cet7k6                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset/blob/master/sascode.sas                                               
                                                                                                                                                                                  
     You can also get the code benind each of the 100 trees.                                                                                                                      
     Tidypredict provides ways to get the code behand other models.                                                                                                               
     Very useful if you want to                                                                                                                                                   
                                                                                                                                                                                  
     [1] (tree number 1 of 100)                                                                                                                                                   
                                                                                                                                                                                  
       if petallength < 3.1 and sepalwidth >= 3.25  then pspecies= "Setosa" ;                                                                                                     
       else if petallength < 2.3 and petalwidth < 1.65 and sepalwidth < 3.25  then pspecies="Setosa" ;                                                                            
           else if   sepallength >= 5.95 and petalwidth >= 1.65 and                                                                                                               
                sepalwidth < 3.25  then pspecies= "Virginica" ;                                                                                                                   
              else if   sepallength < 6.1 and                                                                                                                                     
                  petallength >= 3.1 and sepalwidth >= 3.25  then pspecies= "Versicolor" ;                                                                                        
                else if sepallength >= 6.1 and petallength >= 3.1 and sepalwidth >= 3.25  then pspecies="Virginica" ;                                                             
                  else if   petallength < 5.45 and petallength >= 2.3 and                                                                                                         
                       petalwidth < 1.65 and sepalwidth < 3.25  then pspecies= "Versicolor" ;                                                                                     
                    else if petallength >= 5.45 and petallength >= 2.3 and petalwidth < 1.65 and                                                                                  
                         sepalwidth < 3.25  then pspecies= "Virginica" ;                                                                                                          
                       else if   sepalwidth < 3 and sepallength <                                                                                                                 
                            5.95 and petalwidth >= 1.65 and sepalwidth < 3.25  then pspecies= "Virginica" ;                                                                       
                          else if sepalwidth >= 3 and sepallength < 5.95 and petalwidth >= 1.65 and                                                                               
                          sepalwidth < 3.25  then pspecies= "Versicolor";                                                                                                         
               _                 _                                                                                                                                                
     ___  __ _| |   ___ ___   __| | ___                                                                                                                                           
    / __|/ _` | |  / __/ _ \ / _` |/ _ \                                                                                                                                          
    \__ \ (_| | | | (_| (_) | (_| |  __/                                                                                                                                          
    |___/\__, |_|  \___\___/ \__,_|\___|                                                                                                                                          
            |_|                                                                                                                                                                   
                                                                                                                                                                                  
    github SQL Code                                                                                                                                                               
    https://tinyurl.com/ychfd3nd                                                                                                                                                  
    https://github.com/rogerjdeangelis/utl-r-simple-random-forest-classification-example-using-iris-dataset/blob/master/sqlcode.txt                                               
                                                                                                                                                                                  
    OR IN SQL                                                                                                                                                                     
                                                                                                                                                                                  
    [[1]]                                                                                                                                                                         
    <SQL> CASE                                                                                                                                                                    
    WHEN (`petallength` < 3.1 AND `sepalwidth` >= 3.25) THEN ("Setosa")                                                                                                           
    WHEN (`petallength` < 2.3 AND `petalwidth` < 1.65 AND `sepalwidth` < 3.25) THEN ("Setosa")                                                                                    
    WHEN (`sepallength` >= 5.95 AND `petalwidth` >= 1.65 AND `sepalwidth` < 3.25) THEN ("Virginica")                                                                              
    WHEN (`sepallength` < 6.1 AND `petallength` >= 3.1 AND `sepalwidth` >= 3.25) THEN ("Versicolor")                                                                              
    WHEN (`sepallength` >= 6.1 AND `petallength` >= 3.1 AND `sepalwidth` >= 3.25) THEN ("Virginica")                                                                              
    WHEN (`petallength` < 5.45 AND `petallength` >= 2.3 AND `petalwidth` < 1.65 AND `sepalwidth` < 3.25) THEN ("Versicolor")                                                      
    WHEN (`petallength` >= 5.45 AND `petallength` >= 2.3 AND `petalwidth` < 1.65 AND `sepalwidth` < 3.25) THEN ("Virginica")                                                      
    WHEN (`sepalwidth` < 3.0 AND `sepallength` < 5.95 AND `petalwidth` >= 1.65 AND `sepalwidth` < 3.25) THEN ("Virginica")                                                        
    WHEN (`sepalwidth` >= 3.0 AND `sepallength` < 5.95 AND `petalwidth` >= 1.65 AND `sepalwidth` < 3.25) THEN ("Versicolor")                                                      
    END                                                                                                                                                                           
                                                                                                                                                                                  
    [[2]]                                                                                                                                                                         
    <SQL> CASE                                                                                                                                                                    
    WHEN (`petallength` < 2.35) THEN ("Setosa")                                                                                                                                   
    WHEN (`petallength` < 4.75 AND `petallength` >= 2.35) THEN ("Versicolor")                                                                                                     
    WHEN (`petallength` >= 4.95 AND `petallength` >= 4.75 AND `petallength` >= 2.35) THEN ("Virginica")                                                                           
    WHEN (`petalwidth` < 1.65 AND `petallength` < 4.95 AND `petallength` >= 4.75 AND `petallength` >= 2.35) THEN ("Versicolor")                                                   
    WHEN (`petalwidth` >= 1.65 AND `petallength` < 4.95 AND `petallength` >= 4.75 AND `petallength` >= 2.35) THEN ("Virginica")                                                   
    END                                                                                                                                                                           
    ...                                                                                                                                                                           
    ...                                                                                                                                                                           
    [[100]]                                                                                                                                                                       
    <SQL> CASE                                                                                                                                                                    
    WHEN (`petallength` < 2.45) THEN ("Setosa")                                                                                                                                   
    WHEN (`petalwidth` < 1.7 AND `sepallength` >= 6.25 AND `petallength` >= 2.45) THEN ("Versicolor")                                                                             
    WHEN (`petalwidth` >= 1.7 AND `sepallength` >= 6.25 AND `petallength` >= 2.45) THEN ("Virginica")                                                                             
    WHEN (`petallength` >= 5.35 AND `petalwidth` < 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Virginica")                                                    
    WHEN (`sepallength` < 5.85 AND `petalwidth` >= 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Virginica")                                                    
    WHEN (`petallength` < 4.75 AND `petallength` < 5.35 AND `petalwidth` < 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Versicolor")                           
    WHEN (`sepallength` < 6.0 AND `sepallength` >= 5.85 AND `petalwidth` >= 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Versicolor")                          
    WHEN (`sepallength` >= 6.0 AND `sepallength` >= 5.85 AND `petalwidth` >= 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Virginica")                          
    WHEN (`sepalwidth` < 2.45 AND `petallength` >= 4.75 AND `petallength` < 5.35 AND `petalwidth` < 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Virginica")   
    WHEN (`sepalwidth` >= 2.45 AND `petallength` >= 4.75 AND `petallength` < 5.35 AND `petalwidth` < 1.65 AND `sepallength` < 6.25 AND `petallength` >= 2.45) THEN ("Versicolor") 
    END                                                                                                                                                                           
                                                                                                                                                                                  
               _       _   _                                                                                                                                                      
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                                                                           
    / __|/ _ \| | | | | __| |/ _ \| `_ \                                                                                                                                          
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                                                                         
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                                                                         
                                                                                                                                                                                  
    */                                                                                                                                                                            
                                                                                                                                                                                  
                                                                                                                                                                                  
                                                                                                                                                                                  
    %utlfkil(d:/txt/training.txt);                                                                                                                                                
    %utlfkil(d:/txt/rf_classifier.txt);                                                                                                                                           
    %utlfkil(d:/pdf/rocr.pdf);                                                                                                                                                    
    %utlfkil(d:/pdf/gini.pdf);                                                                                                                                                    
    %utlfkil(d:/pdf/errorbytree.pdf);                                                                                                                                             
    %utlfkil(d:/txt/gettree.txt);                                                                                                                                                 
    %utlfkil(d:/txt/codesas.txt);                                                                                                                                                 
    %utlfkil(d:/txt/sascode.txt);                                                                                                                                                 
    %utlfkil(d:/txt/sqlcode.txt);                                                                                                                                                 
    %utlfkil(d:/pdf/decisiontree.pdf);                                                                                                                                            
                                                                                                                                                                                  
    proc datasets lib=work kill nolist;                                                                                                                                           
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    options validvarname=v7; * important;                                                                                                                                         
                                                                                                                                                                                  
    * input;                                                                                                                                                                      
    libname sd1 "d:/sd1";                                                                                                                                                         
                                                                                                                                                                                  
    data sd1.have(rename=species=Species);                                                                                                                                        
       /* structure the SAS iris data to look like the R iris data */                                                                                                             
       retain sepallength sepalwidth petallength petalwidth Species;                                                                                                              
       set sashelp.iris;                                                                                                                                                          
       array ns[*] _numeric_;                                                                                                                                                     
       do i=1 to dim(ns);                                                                                                                                                         
         ns[i]=ns[i]/10;                                                                                                                                                          
       end;                                                                                                                                                                       
       drop i;                                                                                                                                                                    
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    %utl_submit_r64(resolve('                                                                                                                                                     
    library(dbplyr);                                                                                                                                                              
    library(dplyr);                                                                                                                                                               
    library(tidypredict);                                                                                                                                                         
    library(randomForest);                                                                                                                                                        
    library(ROCR);                                                                                                                                                                
    library(haven);                                                                                                                                                               
    library(SASxport);                                                                                                                                                            
    library(data.table);                                                                                                                                                          
    library(ggraph);                                                                                                                                                              
    library(igraph);                                                                                                                                                              
    /* plot function for decision tree */                                                                                                                                         
    plot_rf_tree <- function(final_model, tree_num, shorten_label = TRUE) {                                                                                                       
      tree <- getTree(rf_classifier,  k = tree_num, labelVar = TRUE) %>%                                                                                                          
        tibble::rownames_to_column() %>%                                                                                                                                          
        mutate(`split point` = ifelse(is.na(prediction), `split point`, NA));                                                                                                     
      graph_frame <- data.frame(from = rep(tree$rowname, 2), to = c(tree$`left daughter`, tree$`right daughter`));                                                                
      graph <- graph_from_data_frame(graph_frame) %>% delete_vertices("0");                                                                                                       
      V(graph)$node_label <- gsub("_", " ", as.character(tree$`split var`));                                                                                                      
      if (shorten_label) { V(graph)$leaf_label <- substr(as.character(tree$prediction), 1, 5) };                                                                                  
      print(tree$prediction);                                                                                                                                                     
      V(graph)$split <- as.character(round(tree$`split point`, digits = 2));                                                                                                      
      print(round(tree$`split point`, digits = 2));                                                                                                                               
      plot <- ggraph(graph, "tree") +                                                                                                                                             
          theme_graph() +                                                                                                                                                         
          geom_edge_link() +                                                                                                                                                      
          geom_node_point() +                                                                                                                                                     
          geom_node_text(aes(label = split), nudge_x = -.3) +                                                                                                                     
          geom_node_label(aes(label = leaf_label, fill = leaf_label), na.rm = TRUE,                                                                                               
                        repel = FALSE, colour = "white", show.legend = FALSE);                                                                                                    
      print(plot);                                                                                                                                                                
    };                                                                                                                                                                            
    set.seed(17);                                                                                                                                                                 
    iris<-read_sas("d:/sd1/have.sas7bdat");                                                                                                                                       
    iris$Species<-as.factor(iris$Species);                                                                                                                                        
    /* Calculate the size of each of the traning and holdout samples: */                                                                                                          
    ind <- sample(2, nrow(iris), replace=TRUE, prob=c(0.7, 0.3));                                                                                                                 
    training    <- iris[ind==1,];                                                                                                                                                 
    validation1 <- iris[ind==2,];                                                                                                                                                 
    /* develop model using the 103 observation training sample */                                                                                                                 
    rf_classifier = randomForest(Species ~ ., data=training, ntree=100, mtry=2, importance=TRUE);                                                                                 
    /* summary report */                                                                                                                                                          
    sink("d:/txt/training.txt");                                                                                                                                                  
    rf_classifier;                                                                                                                                                                
    sink();                                                                                                                                                                       
    /* gini data for plots * condition for sas dataset */                                                                                                                         
    imp  <-rf_classifier$importanceSD[,-1];                                                                                                                                       
    impx <- as.data.table(importance(rf_classifier));                                                                                                                             
    imp  <-cbind(rownames(imp),impx);                                                                                                                                             
    impx$vars<-t(rownames(imp));                                                                                                                                                  
    /* detail meta data on all possible output SAS datasets - like proc contents */                                                                                               
    sink(file="d:/txt/rf_classifier.txt");                                                                                                                                        
    str(rf_classifier);                                                                                                                                                           
    sink();                                                                                                                                                                       
    /* extract the first tree with data that is use for plotting a decision tree */                                                                                               
    sink(file="d:/txt/gettree.txt");                                                                                                                                              
    getTree(rf_classifier, 1, labelVar=TRUE);                                                                                                                                     
    sink();                                                                                                                                                                       
    /* create a text file with sas datastep code tha can be used to run the model in sas */                                                                                                
    sink(file="d:/txt/codesas.txt");                                                                                                                                              
    tidypredict_fit(rf_classifier)[1];                                                                                                                                            
    sink();                                                                                                                                                                       
    /* create a text file with sas sql code tha can be used to run the model in sas */                                                                                                
    sink(file="d:/txt/sqlcode.txt");                                                                                                                                              
    tidypredict_sql(rf_classifier,dbplyr::simulate_mssql());                                                                                                                      
    sink();                                                                                                                                                                       
    /* create highres geni plots */                                                                                                                                               
    pdf(file="d:/pdf/gini.pdf");                                                                                                                                                  
    varImpPlot(rf_classifier);                                                                                                                                                    
    pdf();                                                                                                                                                                        
    /* Validation set assessment #1: looking at confusion matrix */                                                                                                               
    prediction_for_table <- predict(rf_classifier,validation1[,-5]);                                                                                                              
    /* ROC curves and AUC */                                                                                                                                                      
    prediction_for_roc_curve <- predict(rf_classifier,validation1[,-5],type="prob");                                                                                              
    /* Use pretty colours: */                                                                                                                                                     
    pretty_colours <- c("#F8766D","#00BA38","#619CFF");                                                                                                                           
    /* Specify the different classes */                                                                                                                                           
    classes <- levels(validation1$Species);                                                                                                                                       
    pdf(file="d:/pdf/rocr.pdf");                                                                                                                                                  
    pdf();                                                                                                                                                                        
    /* plot decision tree - needs a little more work but is not critical */                                                                                                       
    puc<-c(1,1,1);                                                                                                                                                                
    for (i in 1:3) {                                                                                                                                                              
       true_values <- ifelse(validation1[,5]==classes[i],1,0);                                                                                                                    
       pred <- prediction(prediction_for_roc_curve[,i],true_values);                                                                                                              
       perf <- performance(pred, "tpr", "fpr");                                                                                                                                   
          if (i==1)                                                                                                                                                               
          {plot(perf,main="ROC Curve",col=pretty_colours[i])}                                                                                                                     
          else {plot(perf,main="ROC Curve",col=pretty_colours[i],add=TRUE)};                                                                                                      
       /* Calculate the AUC and print it to screen */                                                                                                                             
       auc.perf <- performance(pred, measure = "auc");                                                                                                                            
       puc[i]<-auc.perf@y.values[[1]];                                                                                                                                            
    };                                                                                                                                                                            
    /* area under roc curves */                                                                                                                                                   
    puc<-as.data.table(t(puc));                                                                                                                                                   
    colnames(puc)<-classes;                                                                                                                                                       
    wantpred<-as.data.table(cbind(validation1[,1:5],prediction_for_table));                                                                                                       
    /* change factor columns to character for sas export */                                                                                                                       
    wantpred[] <- lapply(wantpred, function(x) if(is.factor(x)) as.character(x) else x);                                                                                          
    /* store long column names in the label of the v5 exort file */                                                                                                               
    for (i in seq_along(wantpred)) {label(wantpred[[i]])<- colnames(wantpred)[[i]]};                                                                                              
    pdf(file="d:/pdf/errorbytree.pdf");                                                                                                                                           
    plot(rf_classifier);                                                                                                                                                          
    pdf();                                                                                                                                                                        
    /* decision tree */                                                                                                                                                           
    pdf(file="d:/pdf/decisiontree.pdf");                                                                                                                                          
    plot_rf_tree(rf_classifier,1);                                                                                                                                                
    pdf();                                                                                                                                                                        
    /* create sas error dataset */                                                                                                                                                
    errors<-as.data.table(rf_classifier$err.rate);                                                                                                                                
    for (i in seq_along(imp)) {label(imp[[i]])<- colnames(imp)[[i]]};                                                                                                             
    write.xport(wantpred, puc, imp, errors,file="d:/xpt/want.xpt");                                                                                                               
    '));                                                                                                                                                                          
                                                                                                                                                                                  
                                                                                                                                                                                  
    options ls=171 ps=65;                                                                                                                                                         
                                                                                                                                                                                  
    libname xpt xport "d:/xpt/want.xpt";                                                                                                                                          
                                                                                                                                                                                  
    proc contents data=xpt._all_;                                                                                                                                                 
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    proc datasets lib=work kill;                                                                                                                                                  
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    data predicted(label="Predictions using the holdout sample 47 obs")                                                                                                           
         miss_classified(label="Miss-classified observations using the holdout sample 47 obs") ;                                                                                  
     retain species prediction;                                                                                                                                                   
     %utl_rens(xpt.wantpred);                                                                                                                                                     
     set wantpred(rename=prediction_for_table=prediction);                                                                                                                        
     output predicted;                                                                                                                                                            
     if species ne prediction then output miss_classified ;                                                                                                                       
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    data rocauc(label="area under the ROC curves by Species");                                                                                                                    
      set xpt.puc;                                                                                                                                                                
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    data oob_errors(label="Out of Bag errors by each of the 100 trees");                                                                                                          
    retain tree;                                                                                                                                                                  
      set xpt.errors;                                                                                                                                                             
      tree=_n_;                                                                                                                                                                   
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    data gini(label="GINI equality indexes by flower petals and sepals");                                                                                                         
      %utl_rens(xpt.imp);                                                                                                                                                         
      set imp;                                                                                                                                                                    
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    proc datasets lib=work mt=view nolist;                                                                                                                                        
      delete imp wantpred;                                                                                                                                                        
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    libname xpt clear;                                                                                                                                                            
                                                                                                                                                                                  
    options ls=64 ps=28;                                                                                                                                                          
    proc plot data=oob_errors(obs=25 rename=oob=oob12345678901234567890);                                                                                                         
      plot oob12345678901234567890*tree='*'/box href=14 haxis=0 to 25 by 2;                                                                                                       
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    ods exclude all;                                                                                                                                                              
    ods output observed=wantXpo(rename=label=LEVELS label="Classification matrix classified and miss-classified counts");                                                         
    proc corresp data=predicted dim=1 observed;                                                                                                                                   
    tables species,prediction;                                                                                                                                                    
    run;quit;                                                                                                                                                                     
    ods select all;                                                                                                                                                               
                                                                                                                                                                                  
    /*                                                                                                                                                                            
    Up to 40 obs from WANTXPO total obs=4                                                                                                                                         
                                                                                                                                                                                  
    Obs    LEVELS        Setosa    Versicolor    Virginica    Sum                                                                                                                 
                                                                                                                                                                                  
     1     Setosa          20           0             0        20                                                                                                                 
     2     Versicolor       0          11             1        12                                                                                                                 
     3     Virginica        0           1            14        15                                                                                                                 
     4     Sum             20          12            15        47                                                                                                                 
    */                                                                                                                                                                            
                                                                                                                                                                                  
    proc freq data=predicted;                                                                                                                                                     
     tables species*prediction;                                                                                                                                                   
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    data _null_;                                                                                                                                                                  
                                                                                                                                                                                  
      infile "d:/txt/codesas.txt" firstobs=2 ;                                                                                                                                    
      file "d:/txt/sascode.sas" ;                                                                                                                                                 
                                                                                                                                                                                  
      input;                                                                                                                                                                      
                                                                                                                                                                                  
      if _n_=1 then do;                                                                                                                                                           
          put 'if ';                                                                                                                                                              
          _infile_=scan(_infile_,2,'(');                                                                                                                                          
      end;                                                                                                                                                                        
                                                                                                                                                                                  
      _infile_=prxchange('s/\,/; else if /',-1,_infile_);                                                                                                                         
      _infile_=prxchange('s/\&/and/',-1,_infile_);                                                                                                                                
      _infile_=prxchange('s/\~/then pspecies=/',-1,_infile_);                                                                                                                     
      _infile_=prxchange('s/\)/;/',-1,_infile_);                                                                                                                                  
                                                                                                                                                                                  
      put _infile_;                                                                                                                                                               
      putlog _infile_;                                                                                                                                                            
                                                                                                                                                                                  
    run;quit;                                                                                                                                                                     
                                                                                                                                                                                  
    data sascode(label="Deriving the sas code for tree number one and executing it");                                                                                             
      retain species prediction pspecies;                                                                                                                                         
      length pspecies $16;                                                                                                                                                        
      set predicted;                                                                                                                                                              
      %inc "d:/txt/sascode.sas";                                                                                                                                                  
    run;quit;                                                                                                                                                                     
    ;                                                                                                                                                                             
                                                                                                                                                                                  
                                                                                                                                                                                  
