# About
Automate Selenium-Chrome with Python using my helper class.

# Install requirements 
```
pip install selenium  
pip install webdriver-manager
```

# The bulk
```
## Driver.py

from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager


class Driver:

    def __init__(self):
        self.options = webdriver.ChromeOptions()
        self.driver = ""

    def capabilities(self):
    ## Change this depending on what you need, in this case we are emulating Pixel 2 Phone
        self.options.add_experimental_option("mobileEmulation", {"deviceName": "Pixel 2"})

    def setup(self):
        self.capabilities()
        self.driver = webdriver.Chrome(ChromeDriverManager().install(),
                                       desired_capabilities=self.options.to_capabilities())
        return self.driver

```

# Usage
```
## Your project

from Driver import Driver

driver = Driver().setup()

driver.get("https://www.google.co.uk")
```
