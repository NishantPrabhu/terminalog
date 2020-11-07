# terminalog

A simple utility for clean and aesthetic logging in terminal. Especially useful for tracking machine learning metrics during training or evaluation.

### Installation
```
pip install terminalog
```
termlog is dependent on `termcolor` package, which can be installed as follows:
```
pip install termcolor
```

### Usage
```python
# Import TerminalLogger class from terminalog
from terminalog import TerminalLogger
import random

# Initialize logger
logger = TerminalLogger(float_precision=4)

# A sample training loop 
for epoch in range(10):
    logger.epoch_marker(epoch, total_epochs=10, color='green')
    
    for i, batch in enumerate(data_loader):
        mean_squared_error = random.random()
        binary_crossentropy = random.random()
        
        # Log the metrics to terminal
        logger.log({
            'Batch': i,
            'Mean squared error': mean_squared_error,
            'Binary crossentropy': {'value': binary_crossentropy, 'precision': 6}
        })
```

### License
This package is licensed under the MIT License.
