# Prophet-prebuilt

A fork of Facebook's prophet model that comes with pre-built wheels for Linux, MacOS, Windows. Nothing fancy here, I just forked `main` that has this PR: https://github.com/facebook/prophet/pull/2010#issuecomment-1081934109 and added a step to publish to PyPi. Hopefully, this fork is no longer needed with the official release of Prophet version 1.1. 

I also removed the pystan requirement and will only install CMDSTAN and use CMDSTAN backend. Other than that, there are no modifications to the source code.

## Installation

Wheels are only published for python 3.8. Since we are not using pystan, it should be possible to support python 3.9 and 3.10 but I haven't tested that yet. 

```shell
pip install prophet-prebuilt
```

### Example usage

For more information, consult the offical Prophet page: https://github.com/facebook/prophet

```python
  >>> from prophet import Prophet
  >>> m = Prophet()
  >>> m.fit(df)  # df is a pandas.DataFrame with 'y' and 'ds' columns
  >>> future = m.make_future_dataframe(periods=365)
  >>> m.predict(future)
  ```
