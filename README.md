## Loggoer 

log lib for go 


## Use

```go
package main 


func configLog(logFile, logLevel string) error {
    level := log.DEBUG
    switch strings.ToLower(logLevel) {
    case "debug":
        level = log.DEBUG
    case "info":
        level = log.INFO
    case "warn":
        level = log.WARN
    case "error":
        level = log.ERROR
    }
    lile, err := os.OpenFile(logFile, os.O_WRONLY|os.O_CREATE|os.O_APPEND, 0666)
    if err != nil {
        return err
    }
    log.Set(level, file, log.Lshortfile|log.LstdFlags)
    return nil
}

func main() {
    var logFile string
    var logLevel string 

    err := configureLog(logFile, logLevel)
    // ....
}
```
