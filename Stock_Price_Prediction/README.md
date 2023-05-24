### Predict stock market prices using RNN

1. Make sure 'tensorflow' is installed, first.
2. First, get the whole S&P 500 data from [Yahoo! Finance ^GSPC](https://finance.yahoo.com/quote/%5EGSPC?p=^GSPC)(choose the "Historical Data" option and choose the longest time period). Add the.csv file to "data/SP500.csv" after saving it.
3. Launch the programme "python data_fetcher.py" to download the prices of each stock in the S & P 500 index, which are individually stored to the file "data/stock_abbreviation.csv."
4. To view the command line arguments available, run "python main.py --help".
5. To train the model, run 'python main.py'.


For examples,
- Train a model only on SP500.csv; no embedding
```bash
python main.py --stock_symbol=SP500 --train --input_size=1 --lstm_size=128 --max_epoch=50
```

- Train a model on 100 stocks; with embedding of size 8
```bash
python main.py --stock_count=100 --train --input_size=1 --lstm_size=128 --max_epoch=50 --embed_size=8
```

- Start your Tensorboard
```bash
cd stock-rnn
mkdir logs
tensorboard --logdir ./logs --port 1234 --debug
```

My python environment: 
Python version == 2.7
```
BeautifulSoup==3.2.1
numpy==1.13.1
pandas==0.16.2
tensorflow==1.2.1
urllib3==1.8
scikit-learn==0.16.1
scipy==0.19.1
```