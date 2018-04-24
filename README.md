# Assignment-1.5
1. Create an m x n matrix with replicate(m, rnorm(n)) with m=10 column vectors of n=10 elements each,
constructed with rnorm(n), which creates random normal numbers.
Then we transform it into a dataframe (thus 10 observations of 10 variables) and perform an algebraic
operation on each element using a nested for loop: at each iteration, every element referred by the two
indexes is incremented by a sinusoidal function, compare the vectorized and non-vectorized form of creating
the solution and report the system time differences.

                        m = 10 #number of rows
                        n = 10 # number of columns

                        # Class: Dataframe
                        st = print(Sys.time())
                        X <- replicate(m, rnorm(n))
                        X <- data.frame(X)

                        for(i in 1:m)
                        {
                         for(j in 1:n)
                         {
                          X[i, j] = X[i,j] + sin(X[i,j])
                         }
                        }
                        end = print(Sys.time())
                        run = end - st
                        X
                        run

                        # Class: Vector
                        st = print(Sys.time())
                        K <- replicate(m, rnorm(n))
                        K <- as.vector(K)
                        for(i in 1:(m*n))
                        { 
                         K[i] = K[i] + sin(K[i])
                        }
                        end = print(Sys.time())
                        run = end - st
                        K


                        # Y <- replicate(m, rnorm(n))
                        # Y
                        run

