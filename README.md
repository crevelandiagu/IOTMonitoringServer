# Prueba Semana 6

El codigo modificado esta en control donde se modifica 
la funcion para tener tres mediciones un healtcheck y la medicion
de luminisencia.

En los archivos **IOTDeviceScript_cristian.ino** y **IOTDeviceScript_jose.ino**
se encuentra el codigo del arduino que se ejecuto en cada computado.
Y en cada uno de los archivos esta la linea de:

### Cristian
```python
 String data = "{";
  data += "\"temperatura\": "+ String(temperatura, 1) +", ";
  data += "\"humedad\": "+ String(humedad, 1) +", ";
  data += "\"luminosidad\": "+ String(luminosidad, 1);
  data += "}";
  char payload[data.length()+1];
  data.toCharArray(payload,data.length()+1);
```

### Jose 
```python
void sendSensorData(float temperatura, float humedad, float luminosidad) {
  String data = "{";
  data += "\"temperatura\": "+ String(temperatura, 1) +", ";
  data += "\"humedad\": "+ String(humedad, 1) +", ";
  data += "\"intencidadLuz\": "+ String(luminosidad, 1);
  data += "}";
  char payload[data.length()+1];
  data.toCharArray(payload,data.length()+1);
  
  client.publish(MQTT_TOPIC_PUB, payload);
}
```

