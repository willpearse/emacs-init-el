clr <- function(x){
    rm(list=ls())
    source("~/.Rprofile")
}
prog.bar <- function(x, y){
    if(y < 100){
        cat(".")} else {
            z <- Filter(function(z) z>=0, seq(1,y,length.out=100)-x)
            if(length(z) > 0)
                tryCatch(if(z[1] < 1) if((length(z) %% 10)==0) cat("|") else cat("."), error=function(z) cat("."))
        }
}    
.sample <- function(x, size, replace=FALSE, prob=NULL)
    if(length(x) == 1) x else sample(x, size, replace, prob)
sourceDir <- function(path, trace = TRUE, ...) {
    for (nm in list.files(path, pattern = "\\.[RrSsQq]$")) {
       if(trace) cat(nm,":")           
       source(file.path(path, nm), ...)
       if(trace) cat("\n")
    }
}
comp.vecs <- function(x, y){
    x <- unique(x);y <- unique(y)
    in.x <- length(intersect(x,y))
    unique.x <- length(setdiff(x,y))
    unique.y <- length(setdiff(y,x))
    output <- matrix(c(unique.x,unique.y,in.x,in.x), 2, 2, byrow=TRUE, dimnames=list(c("unique","shared"),c("x","y")))
    return(output)
}
plt.mod <- function(x, ...){
    old.par <- par(mfrow=c(2,2))
    plot(x, ...)
    par(old.par)
}
logit <- function(x)
    log(x / (1-x))
inv.logit <- function(x)
    exp(x) / (exp(x)+1)

local({
  r <- getOption("repos")
  r["CRAN"] <- "https://cran.cnr.berkeley.edu/"
  options(repos = r)
})
