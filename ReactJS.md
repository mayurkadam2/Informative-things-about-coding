### Difference between onClick={() => props.delete(props.cardKey)} vs onClick={props.delete(props.cardKey)}


| Aspect                  | onClick={() => props.delete(props.cardKey)} | onClick={props.delete(props.cardKey)} |
|------------------------|--------------------------------------------|--------------------------------------|
| Syntax Validity        | ✅ Correct                                  | ❌ Incorrect usage                    |
| Function Passed?       | Yes (function reference)                   | No (function result is passed)       |
| Execution Time         | On user click                              | During render                        |
| Behavior               | Runs when button is clicked                | Runs immediately                     |
| onClick Value          | A function                                | Return value (often undefined)       |
| Works as Expected?     | ✅ Yes                                     | ❌ No                                |
| Use Case               | When passing arguments                     | Never recommended                    |
| Example Output         | Deletes item on click                      | Deletes item instantly               |


---

### Passing Fucntion as a props
- it is like changing the variables in the parent from child
- we just pass reference to the children

**The Props passed to the children will look like this**
```
// When parent renders this:
<Child sendData={handleData} name="Mayur" />

// React internally creates this object and hands it to Child:
props = {
  sendData: [reference to handleData function @ 0x4A2F],
  name: "Mayur"
}
```

```
PARENT SCOPE
┌─────────────────────────────────────────┐
│                                         │
│  const [data, setData] = useState("")   │
│                                         │
│  const handleData = (val) => {          │◄─────────────────────┐
│    setData(val)  // runs HERE           │                      │
│  }  @ memory: 0x4A2F                    │                      │
│                                         │               function runs
│  return <Child sendData={handleData} /> │              in PARENT scope
└─────────────────────────────────────────┘                    ▲
                     │                                         │
           passes reference 0x4A2F                             │
                     │                                         │  
                     ▼                                   child calls it
CHILD SCOPE                                             like a phone call
┌─────────────────────────────────────────┐                    │
│                                         │                    │
│  props = {                              │                    │
│    sendData: → 0x4A2F  (read only )     │                    │
│  }                                      │                    │
│                                         │                    │
│  <button                                │                    │
│    onClick={() => props.sendData("hi")} ├────────────────────┘
│  >                                      │   calling, not mutating
└─────────────────────────────────────────┘
```
