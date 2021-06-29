# ArduinoLSM6DSOX library

## Methods

### `begin()`

Initialize the IMU.

#### Syntax 

```
IMU.begin()
```

#### Parameters

None.

#### Returns

1 on success, 0 on failure.

#### Example

```
if (!IMU.begin()) {
    Serial.println("Failed to initialize IMU!");
    while (1);
}
```

#### See also

* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `end()`

De-initialize the IMU.

#### Syntax 

```
IMU.end()
```

#### Parameters

None.

#### Returns

None.

#### Example

```
if (!IMU.begin()) {
    Serial.println("Failed to initialize IMU!");
    while (1);
}

// Read IMU data...

// Done with the IMU readings
IMU.end();
```

#### See also

* [begin()](#begin)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `readAcceleration()`

Query the IMU's accelerometer and return the acceleration in g's. 

#### Syntax 

```
IMU.readAcceleration(x,y,z)
```

#### Parameters

* _x_: float variable where the acceleration value in the IMU's x-axis will be stored.
* _y_: float variable where the acceleration value in the IMU's y-axis will be stored.
* _z_: float variable where the acceleration value in the IMU's z-axis will be stored.

#### Returns

1 on success, 0 on failure.

#### Example

```
float x, y, z;

if (IMU.accelerationAvailable()) {
    IMU.readAcceleration(x, y, z);

    Serial.print(x);
    Serial.print('\t');
    Serial.print(y);
    Serial.print('\t');
    Serial.println(z);
}
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `readGyroscope()`

Query the IMU's gyroscope and return the angular speed in dps (degrees per second).

#### Syntax 

```
IMU.readGyroscope(x,y,z)
```

#### Parameters

* _x_: float variable where the gyroscope value in the IMU's x-axis will be stored.
* _y_: float variable where the gyroscope value in the IMU's y-axis will be stored.
* _z_: float variable where the gyroscope value in the IMU's z-axis will be stored.

#### Returns

1 on success, 0 on failure.

#### Example

```
float x, y, z;

if (IMU.gyroscopeAvailable()) {
    IMU.readGyroscope(x, y, z);

    Serial.print(x);
    Serial.print('\t');
    Serial.print(y);
    Serial.print('\t');
    Serial.println(z);
}
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `accelerationAvailable()`

Query if new acceleration data from the IMU is available.

#### Syntax 

```
IMU.accelerationAvailable()
```

#### Parameters

None.

#### Returns

0 if no new acceleration data is available, 1 if new acceleration data is available.

#### Example

```
float x, y, z;

if (IMU.accelerationAvailable()) {
    IMU.readAcceleration(x, y, z);

    Serial.print(x);
    Serial.print('\t');
    Serial.print(y);
    Serial.print('\t');
    Serial.println(z);
}
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `gyroscopeAvailable()`

Query if new gyroscope data from the IMU is available.

#### Syntax 

```
IMU.gyroscopeAvailable()
```

#### Parameters

None.

#### Returns

0 if no new gyroscope data is available, 1 if new gyroscope data is available.

#### Example

```
float x, y, z;

if (IMU.gyroscopeAvailable()) {
    IMU.readGyroscope(x, y, z);

    Serial.print(x);
    Serial.print('\t');
    Serial.print(y);
    Serial.print('\t');
    Serial.println(z);
}
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `accelerationSampleRate()`

Return the IMU's accelerometer sample rate.

#### Syntax 

```
IMU.accelerationSampleRate()
```

#### Parameters

None.

#### Returns

The IMU's accelerometer sample rate in Hz.

#### Example

```
Serial.print("Accelerometer sample rate = ");
Serial.print(IMU.accelerationSampleRate());
Serial.println(" Hz");
Serial.println();
Serial.println("Acceleration in g's");
Serial.println("X\tY\tZ");
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `gyroscopeSampleRate()`

Return the IMU's gyroscope sample rate.

#### Syntax 

```
IMU.gyroscopeSampleRate()
```

#### Parameters

None.

#### Returns

The IMU's gyroscope sample rate in Hz.

#### Example

```
Serial.print("Gyroscope sample rate = ");
Serial.print(IMU.gyroscopeSampleRate());
Serial.println(" Hz");
Serial.println();
Serial.println("Angular speed in degrees/second");
Serial.println("X\tY\tZ");
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `readMagneticField()`

Query the IMU's magnetometer and return the magnetic field in uT (micro Tesla).

#### Syntax 

```
IMU.readMagneticField(x,y,z)
```

#### Parameters

* _x_: float variable where the magnetometer value in the IMU's x-axis will be stored.
* _y_: float variable where the magnetometer value in the IMU's y-axis will be stored.
* _z_: float variable where the magnetometer value in the IMU's z-axis will be stored.

#### Returns

1 on success, 0 on failure.

#### Example

```
float x, y, z;

if (IMU.magneticFieldAvailable()) {
    IMU.readMagneticField(x, y, z);

    Serial.print(x);
    Serial.print('\t');
    Serial.print(y);
    Serial.print('\t');
    Serial.println(z);
}
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [magneticFieldSampleRate()](#magneticFieldSampleRate)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `magneticFieldSampleRate()`

Return the IMU's magnetometer sample rate.

#### Syntax 

```
IMU.magneticFieldSampleRate()
```

#### Parameters

None.

#### Returns

The IMU's magnetometer sample rate in Hz.

#### Example

```
Serial.print("Magnetic Field sample rate = ");
Serial.print(IMU.magneticFieldSampleRate());
Serial.println(" Hz");
Serial.println();
Serial.println("Magnetic Field in uT");
Serial.println("X\tY\tZ");
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldAvailable()](#magneticFieldAvailable)

### `magneticFieldAvailable()`

Query if new magnetic field data from the IMU is available.

#### Syntax 

```
IMU.magneticFieldAvailable()
```

#### Parameters

None.

#### Returns

0 if no new magnetic field data is available, 1 if new magnetic field data is available.

#### Example

```
float x, y, z;

if (IMU.magneticFieldAvailable()) {
    IMU.readMagneticField(x, y, z);

    Serial.print(x);
    Serial.print('\t');
    Serial.print(y);
    Serial.print('\t');
    Serial.println(z);
}
```

#### See also

* [begin()](#begin)
* [end()](#end)
* [readAcceleration()](#readAcceleration)
* [readGyroscope()](#readGyroscope)
* [accelerationAvailable()](#accelerationAvailable)
* [gyroscopeAvailable()](#gyroscopeAvailable)
* [accelerationSampleRate()](#accelerationSampleRate)
* [gyroscopeSampleRate()](#gyroscopeSampleRate)
* [readMagneticField()](#readMagneticField)
* [magneticFieldAvailable()](#magneticFieldAvailable)