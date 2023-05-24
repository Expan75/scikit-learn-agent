# scikit-learn monitoring agent

There exists a vast amount of options for monitoring of scikit-learn models. Ironically, few manage to attain the simplicity of the scikit-learn API and user experience. Ideally, we'd like something we can drop at any point in our model pipeline and get metrics exported to our favourite observability stack; sklearn-agent aims to be that piece.

# USP in a nutshell

```python

agent = ScikitAgent(project="churn-v2")

pipe = Pipeline([
    ("input_monitor", agent),
    ("scaler", StandardScaler()), 
    ("svc", SVC()),
    ("output_monitor", agent),
])

# proceed as you would, with any deployment pipeline!
pipe.fit(X)
```
