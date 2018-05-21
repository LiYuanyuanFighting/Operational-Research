    Below are the model and data files used in CPLEX Optimization Studio for solving setCovering problem  
    in cousera, see the [link](https://github.com/LiYuanyuanFighting/setcover)  
    /*********************************************
     * OPL 12.8.0.0 Model
     * Author: yuanyuanli
     * Creation Date: May 21, 2018 at 2:51:20 PM
     *********************************************/
    
    // Problem size 
    int n=...; // number of items
    range items=1..n;
    
    int m =...;	// number of fire stations
    range fireStations = 1..m;
    
    dvar boolean x[fireStations];
    
    int A[fireStations][items] = ...; // Coverture matrix
    int c[fireStations] = ...;	// Cost vector
    
    // Objective function:
    minimize sum(j in fireStations) c[j]*x[j];
    
    // Constraints
    subject to{
    
    forall( i in items )
      sum(j in fireStations)
        A[j][i]*x[j] >= 1;
    }
   
    /*********************************************
     * OPL 12.8.0.0 Data
     * Author: yuanyuanli
     * Creation Date: May 21, 2018 at 2:51:30 PM
     *********************************************/   
    m = 4;
    n = 5;
    
    A = [
    [1 0 1 0 0]
    [0 1 1 1 0]
    [0 1 0 0 1]
    [0 0 0 0 1]
    ];
    
    c = [12 7 10 5];

    
    
