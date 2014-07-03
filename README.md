# Functional Patterns
=====================

## State/Event Pattern
* State is derived from previous state + input
* Many diverse inputs
* Need to recover past states
* Need to visualize previous state

```clojure
(defn end-state [start-state events]
  (reduce update-state start-state events))
```

## Consequences Pattern
* Eache event an trigger multiple events
* Genereated events cause state changes
* Neet to visualize intermadiate states

```clojure
(defn conequences [current-state event]
  (reduce update-state current-state
    (consequences current-state event)))
```
