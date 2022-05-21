## localStorage.setItem()

1. localStorage.setItem()
    - takes two arguments: 
        - key (in double quotes)
        - variable to be stored
            - use JSON.stringify to store objects as strings

## useEffect() - to set state

2. useEffect() hook takes an anonymous arrow function as an argument where the body is a localStorage.setItem() method call.
    - ex:

```
useEffect(() => {
    localStorage.setItem("submissions", JSON.stringify(submissions));
    localStorage.setItem("nameA", nameA);
    localStorage.setItem("nameB", nameB);
})
```

## localStorage.getItem()

3. localStorage.getItem()
    - takes one argument:
        - the key of the data (in double quotes)
    - wrap localStorage.getItem() in JSON.parse() if the key returns an object that has been stringified.

## useState() to get state

4. useState takes an arrow function as an argument where the body is the localStorage.getItem() method call + || OR logical operator + default value to fall back on if nothing has been written to localStorage.
    - ex:

```
const [state, setState] = useState(() => JSON.parse(localStorage.getItem("state")) || []);
```