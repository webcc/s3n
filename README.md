# Simple Semantic Sensor Network (s3n)

Simplified Semantic Sensor Network vocabulary partially based upon the 
[Semantic Sensor Network Ontology](http://purl.oclc.org/NET/ssnx/ssn) from the
W3C.

A full implementation of the SSN vocabulary may not be suitable for some sensor
networks where the overhead of a complete OWL ontology imposes several 
restrictions on information exchange, performance and interoperability in 
common web of things environments.

## Introduction

The RDF representation of the vocabulary defined by this document uses the 
namespace `https://imergo.com/ns/2015/s3n#`. The prefix `s3n` is used 
throughout this document to denote this namespace. Other prefixes used 
here include:

| Namespace | Prefix | Description |
| --------- | ------ | ----------- |
| http://purl.org/dc/terms/ | dct | Dublin Core Terms namespace |
| http://www.w3.org/1999/02/22-rdf-syntax-ns# | rdf | RDF namespace |
| http://www.w3.org/2000/01/rdf-schema# | rdfs | RDF Schema namespace |
| http://www.w3.org/2001/XMLSchema# | xsd | XML Schema namespace |

## Classes

| Class Name | Label | Description | Related Properties |
| ---------- | ----- | ----------- | ------------------ |
| **[s3n:Device](#Device)** | Device | A device is a physical piece of technology - a system in a box. Devices may of course be built of smaller devices and software components (i.e. systems have components). | `dct:title` <br> `dct:description` <br> `dct:hasPart` |
| **[s3n:Sensor](#Sensor)** | Sensor | Sensors may be physical devices, computational methods, a laboratory setup with a person following a method, or any other thing that can follow a method to observe a property. | [s3n:observes](#observes) <br> [s3n:detects](#detects) <br> [s3n:hasMeasurementCapability](#hasMeasurementCapability) |
| [s3n:Observation](#Observation) | Observation |A situation in which a Sensing method has been used to estimate or calculate a value of a Property. | [s3n:observedBy](#observedBy) <br>[s3n:observedProperty](#observedProperty) <br>[s3n:observationResult](#observationResult) <br>[dct:includesEvent](http://www.loa-cnr.it/ontologies/DUL.owl#includesEvent) <br>[s3n:observationResultTime](#observationResultTime)
| [s3n:SensorInput](#SensorInput) | SensorInput |An Event in the real world that 'triggers' the sensor| 
| [s3n:SensorOutput](#SensorOutput) | SensorOutput |A sensor outputs a piece of information, the value itself being represented by an ObservationValue| [s3n:isProducedBy](#isProducedBy) <br>[s3n:hasValue](#hasValue) 
| [s3n:Condition](#Condition) | Condition |Used to specify ranges for qualities that act as conditions on a system/sensor's operation| 
| [s3n:MeasurementCapability](#MeasurementCapability) |Measurement Capability|Collects together measurement properties and the environmental conditions in which those properties hold| [s3n:hasCondition](#hasCondition) <br>[s3n:hasMeasurementProperty](#hasCondition)
| [s3n:ObservationValue](#ObservationValue)| Observation Value |The value of the result of an Observation| 
| [s3n:MeasurementProperty](#MeasurementProperty)| Measurement Property|An identifiable and observable characteristic of a sensor's observations or ability to make observations| 
| [s3n:Accuracy](#Accuracy) | Accuracy |The closeness of agreement between the value of an observation and the true value of the observed quality| | 
| [s3n:Frequency](#Frequency) | Frequency |The smallest possible time between one observation and the next| |
| [s3n:Precision](#Precision) | Precision |The closeness of agreement between replicate observations on an unchanged or similar quality value| |
| [s3n:Resolution](#Resolution) | Resolution |The smallest difference in the value of a quality being observed that would result in perceptably different values of observation results| |
| [s3n:ResponseTime](#ResponseTime) | Response Time |The time between a change in the value of an observed quality and a sensor 'settling' on an observed value.| |
| [s3n:Sensitivity](#Sensitivity) | Sensitivity |Sensitivity is the quotient of the change in a result of sensor and the corresponding change in a value of a quality being observed| |

<h3 id="Device">Device</h3>

- **Label**: Device (`https://imergo.com/ns/2015/s3n#Device`)
- **Description**: A device is a physical piece of technology - a system in a
  box. Devices may of course be built of smaller devices and software
  components (i.e. systems have components).
- **Domain of**:
- **Range of**:
- **Related properties**:
  + dct:title 
  + dct:description
  + dct:hasPart

<h3 id="Sensor">Sensor</h3>

- **Label**: Sensor (`https://imergo.com/ns/2015/s3n#Sensor`)
- **Description**: Sensors may be physical devices, computational methods, a
  laboratory setup with a person following a method, or any other thing that
  can follow a method to observe a property
- **Domain of**:
- **Range of**:
- **Related properties**:
  + dct:title 
  + dct:description
  + dct:hasPart

<h3 id="Observation">Observation</h3>

An Observation is a Situation in which a Sensing method has been used to estimate or calculate a value of a Property. 

<h3 id="Condition">Condition</h3>

Used to specify ranges for qualities that act as conditions on a system/sensor's operation

<h3 id="ObservationValue">ObservationValue</h3>

The value of the result of an Observation. An Observation has a result which is the output of some sensor, the result is an information object that encodes some value for a Feature.

<h3 id="MeasurementCapability">MeasurementCapability</h3>

Collects together measurement properties (accuracy, range, precision, etc) and the environmental conditions in which those properties hold, representing a specification of a sensor's capability in those conditions. 

<h3 id="MeasurementProperty">MeasurementProperty</h3>

An identifiable and observable characteristic of a sensor's observations or ability to make observations.

<h3 id="SensorInput">SensorInput</h3>

An Event in the real world that 'triggers' the sensor. 

<h3 id="SensorOutput">SensorOutput</h3>

A sensor outputs a piece of information (an observed value), the value itself being represented by an ObservationValue.

<h3 id="Property">Property</h3>

An observable Quality of an Event or Object.

### Accuracy

The closeness of agreement between the value of an observation and the true value of the observed quality.

### Frequency

The smallest possible time between one observation and the next.

### Precision

The closeness of agreement between replicate observations on an unchanged or similar quality value: i.e., a measure of a sensor's ability to consitently reproduce an observation.

### Resolution

The smallest difference in the value of a quality being observed that would result in perceptably different values of observation results.

### ResponseTime

The time between a (step) change inthe value of an observed quality and a sensor (possibly with specified error) 'settling' on an observed value.

### Sensitivity

Sensitivity is the quotient of the change in a result of sensor and the corresponding change in a value of a quality being observed.

## Properties

Class Name | Label | Domain | Range 
:----------: |:-----: |:-----------: |:------------------
| [s3n:detects](#detects) | detects | [s3n:Sensor](#Sensor) | [s3n:SensorInput](#SensorInput)
| [s3n:observes](#observes) | Sensor | [s3n:Sensor](#Sensor) | [s3n:Property](#Property)
| [s3n:hasMeasurementCapability](#hasMeasurementCapability) | hasMeasurementCapability | [s3n:Sensor](#Sensor) | [s3n:MeasurementCapability](#MeasurementCapability) 
| [s3n:observedProperty](#observedProperty) | observedProperty | [s3n:Observation](#Observation) | [s3n:Property](#Property)
| [s3n:observationResult](#observationResult) | observationResult | [s3n:Observation](#Observation) | [s3n:SensorOutput](#Output)
| [s3n:isProducedBy](#isProducedBy) | isProducedBy | [s3n:SensorOutput](#SensorOutput) | [s3n:Sensor](#Sensor)
| [s3n:observedBy](#observedBy) | observedBy | [s3n:Observation](#Observation) | [s3n:Sensor](#Sensor) 
| [s3n:hasMeasurementProperty](#hasMeasurementProperty) | hasMeasurementProperty | [s3n:MeasurementCapability](#MeasurementCapability) | [s3n:MeasurementProperty](#MeasurementProperty)
 
<h3 id="detects">detects</h3>

A relation from a sensor to the Stimulus(input) that the sensor can detect.

- Domain: [s3n:Sensor](#Sensor)
- Range: [s3n:SesorInput](#SensorInput)

<h3 id="observes">observes</h3>

Relation between a Sensor and a Property that the sensor can observe.

- Domain: [s3n:Sensor](#Sensor)
- Range: [s3n:Property](#Property)

<h3 id="hasMeasurementCapability">hasMeasurementCapability</h3>

Relation from a Sensor to a MeasurementCapability describing the measurement properties of the sensor.

- Domain: [s3n:Sensor](#Sensor)
- Range: [s3n:MeasurementCapability](#MeasurementCapability)

<h3 id="observedProperty">observedProperty</h3>

Relation linking an Observation to the Property that was observed.

- Domain: [s3n:Observation](#Observation)
- Range: [s3n:Property](#Property)

<h3 id="observationResult">observationResult</h3>

Relation linking an Observation (i.e., a description of the context, the
Situation, in which the observatioin was made) and a Result, which contains a
value representing the value associated with the observed Property.

- Domain: [s3n:Observation](#Observation)
- Range: [s3n:SensorOutput](#SensorOutput)

<h3 id="isProducedBy">isProducedBy</h3>

Relation between a producer and a produced entity: for example, between a
 sensor and the produced output.
 
- Domain: [s3n:SensorOutput](#SensorOutput)
- Range: [s3n:Sensor](#Sensor)

<h3 id="observedBy">observedBy</h3>

Relation between an Observation and Sensor.

- Domain: [s3n:Observation](#Observayion)
- Range: [s3n:Sensor](#Sensor)

<h3 id="hasMeasurementProperty">hasMeasurementProperty</h3>

Relation from a MeasurementCapability to a MeasurementProperty:

- Domain: [s3n:MeasurementCapability](#MeasurementCapability)
- Range: [s3n:MeasurementProperty](#MeasurementProperty)
