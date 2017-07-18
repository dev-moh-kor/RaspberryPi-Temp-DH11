# RaspberryPi-Temp-DH11
Install the ADAFRUIT DHT library from Github:
Python GPIO library:

    sudo apt-get install build-essential python-dev python-pip
    sudo pip install RPi.GPIO
Python Imaging library:

    sudo apt-get install python-imaging python-smbus
Adafruit SSD1306 Python library:

    sudo apt-get install git
    git clone https://github.com/adafruit/Adafruit_Python_SSD1306.git

    cd Adafruit_Python_SSD1306; sudo python setup.py install

Detect Oled connection 
    
    sudo apt-get install i2c-tools

Check connection:

    sudo i2cdetect -y 1

Create the python script ex: dht.py

    # Importeer Adafruit DHT bibliotheek.
    import Adafruit_DHT
 
    humidity, temperature = Adafruit_DHT.read_retry(Adafruit_DHT.DHT11, 4)
 
    humidity = round(humidity, 2)
    temperature = round(temperature, 2)
 
    if humidity is not None and temperature is not None:
    print 'Temperatuur = {0:0.1f}C' '\n'  'Luchtvochtigheid = {1:0.1f}%'.format(temperature, humidity)
    else:
    print 'Kan de sensor niet uitlezen!'
    
correcte xml format:
    
    # Importeer Adafruit DHT bibliotheek.
    
    
    import Adafruit_DHT

    humidity, temperature = Adafruit_DHT.read_retry(Adafruit_DHT.DHT11, 4)

    humidity = round(humidity, 2)
    temperature = round(temperature, 2)

    if humidity is not None and temperature is not None:
      print '<?xml version="1.0" encoding="utf-8"?>'
      print '<data>'
      print '<temperatuur>{0:0.1f}</temperatuur>'.format(temperature, humidity)
      print '<luchtvochtigheid>{1:0.1f}</luchtvochtigheid>'.format(temperature, humidity)
      print '</data>'
    else:
      print 'Kan de sensor niet uitlezen!'
    
    


Alternative:

    git clone https://github.com/adafruit/Adafruit_Python_DHT.git
    cd Adafruit_Python_DHT
    
    sudo apt-get update
    sudo apt-get install build-essential python-dev python-openssl
    
    sudo python setup.py install
