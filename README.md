# IOT with MQTT Publish Subscribe Sample with AWS IOT

This sample simulate a temperature sensor and communicate using MQTT protocol to AWS IOT.
Each sensors send it's temperature to a topic, and in the same time receive messaage from other sensors.
This is only an example. Real case may not be like this.

This sample is taken / modified from
https://docs.aws.amazon.com/iot/latest/developerguide/iot-device-sdk-node.html

## Step to do:
Install nodejs in your machine (any machine, PC, Laptop, Linux, Raspberry, Arduino)

## Get the source code from
https://github.com/ramotlubis/binus-iot/tree/iot-mqtt

## How to run:
change parameter nim:
--nim 11001 is your NIM (students ID)

Open 2 devices or 2 terminal

First device / terminal, run this command:
```bash
node device-example -k "../certs/fbd7e09f89-private.pem.key" -c "../certs/fbd7e09f89-certificate.pem.crt" -i node—client-1 -a "../certs/AmazonRootCA1.pem" -H "a2q9331avx1cno-ats.iot.ap-southeast-1.amazonaws.com" -p 8883 -T "home-temp-sensor" --test-mode 1 --nim 11001
```
Second device / terminal, run this command:
```bash
node device-example -k "../certs/fbd7e09f89-private.pem.key" -c "../certs/fbd7e09f89-certificate.pem.crt" -i node—client-2 -a "../certs/AmazonRootCA1.pem" -H "a2q9331avx1cno-ats.iot.ap-southeast-1.amazonaws.com" -p 8883 -T "home-temp-sensor" --test-mode 2 --nim 11001
```

## Expected Result:

Result on Machine / Terminal one:
```bash
[node—client-1-11001]New message received!
[node—client-1-11001]Topic :topic_1
[node—client-1-11001]Message Content:{"mode2Process":"28.15","sender":"node—client-2"}

[node—client-1-11001]New message received!
[node—client-1-11001]Topic :topic_1
[node—client-1-11001]Message Content:{"mode2Process":"26.22","sender":"node—client-2"}

[node—client-1-11001]New message received!
[node—client-1-11001]Topic :topic_1
[node—client-1-11001]Message Content:{"mode2Process":"20.98","sender":"node—client-2"}


```

Result on Machine / Terminal two:
```bash
[node—client-2-11001]New message received!
[node—client-2-11001]Topic :topic_2
[node—client-2-11001]Message Content:{"Message":"[SensorClientID:node—client-1. SensorTime: 1585910242684] Sensor Temperature  = 31.15","Sender":"node—client-1"}

[node—client-2-11001]New message received!
[node—client-2-11001]Topic :topic_2
[node—client-2-11001]Message Content:{"Message":"[SensorClientID:node—client-1. SensorTime: 1585910246687] Sensor Temperature  = 20.04","Sender":"node—client-1"}

[node—client-2-11001]New message received!
[node—client-2-11001]Topic :topic_2
[node—client-2-11001]Message Content:{"Message":"[SensorClientID:node—client-1. SensorTime: 1585910250688] Sensor Temperature  = 21.55","Sender":"node—client-1"}

[node—client-2-11001]New message received!
[node—client-2-11001]Topic :topic_2
[node—client-2-11001]Message Content:{"Message":"[SensorClientID:node—client-1. SensorTime: 1585910254689] Sensor Temperature  = 31.09","Sender":"node—client-1"}


```



## Questions?
Please send your question from Binusmaya forum 

