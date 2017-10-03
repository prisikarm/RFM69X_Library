This is a modified RFM69 library used for ESP-32 processor.
It is motivated by the fact the ESP-32 SPI transactions are managed as interrupt while the RFM69 library starts SPI transactions in interrupt routine simultaneously.
The main change is the move from the SPI transactions from the interruptHandler function, to a new one; the interruptHandling, which is tested during the receiveDone.
This version works in a mix environment (RFM69 and RFM69X libraries), however it is incompatible with virtualised versions such as the RFM_ATC one.

 Notes :
  * The virtualised RFM69_SessionKey for ESP-32 is available (see RFM69X_SessionKey)
  * It also implement the SPI_HAS_TRANSACTION syntax from the recent SPI Library
  * A test of the presence or good functioning of the RFM transceiver is also added.
  * Because SPI transaction is now moved out of the interrupt routine, this version is also compatible with Ethernet Shield (W5100) without further modifications
  * This version is tested on ARDUINO UNO, ARDUINO MEGA 2560, Moteino R6, MoteinoMEGA, ESP-32 (WeMoS LOLIN 32) and ESP8266 (WeMoS D1 mini)
  * From the time being running on ESP-32 seems to be a little bit slower that on other processors.
