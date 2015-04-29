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

| Class Name | Label | Description | Properties |
| ---------- | ----- | ----------- | ---------- |
| [s3n:Device][#device] | Device | A device is a physical piece of technology -
  a system in a box. Devices may of course be built of smaller devices and 
  software components (i.e. systems have components). |
  dct:title <br> dct:description <br> dct:hasPart |
| [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor) | Sensor |Any thing that can follow a sensing Method to observe a Property | [s3n:observes](https://imergo.com/ns/2015/s3n#observes) <br>[s3n:detects](https://imergo.com/ns/2015/s3n#detects) <br>[s3n:hasMeasurementCapability](https://imergo.com/ns/2015/s3n#hasMeasurementCapability) 
| [s3n:Observation](https://imergo.com/ns/2015/s3n#Observation) | Observation |A situation in which a Sensing method has been used to estimate or calculate a value of a Property. | [s3n:observedBy](https://imergo.com/ns/2015/s3n#observedBy) <br>[s3n:observedProperty](https://imergo.com/ns/2015/s3n#observedProperty) <br>[s3n:observationResult](https://imergo.com/ns/2015/s3n#observationResult) <br>[dct:includesEvent](http://www.loa-cnr.it/ontologies/DUL.owl#includesEvent) <br>[s3n:observationResultTime](https://imergo.com/ns/2015/s3n#observationResultTime)
| [s3n:SensorInput](https://imergo.com/ns/2015/s3n#SensorInput) | SensorInput |An Event in the real world that 'triggers' the sensor| 
| [s3n:SensorOutput](https://imergo.com/ns/2015/s3n#SensorOutput) | SensorOutput |A sensor outputs a piece of information, the value itself being represented by an ObservationValue| [s3n:isProducedBy](https://imergo.com/ns/2015/s3n#isProducedBy) <br>[s3n:hasValue](https://imergo.com/ns/2015/s3n#hasValue) 
| [s3n:Condition](https://imergo.com/ns/2015/s3n#Condition) | Condition |Used to specify ranges for qualities that act as conditions on a system/sensor's operation| 
| [s3n:MeasurementCapability](https://imergo.com/ns/2015/s3n#MeasurementCapability) |Measurement Capability|Collects together measurement properties and the environmental conditions in which those properties hold| [s3n:hasCondition](https://imergo.com/ns/2015/s3n#hasCondition) <br>[s3n:hasMeasurementProperty](https://imergo.com/ns/2015/s3n#hasCondition)
| [s3n:ObservationValue](https://imergo.com/ns/2015/s3n#ObservationValue)| Observation Value |The value of the result of an Observation| 
| [s3n:MeasurementProperty](https://imergo.com/ns/2015/s3n#MeasurementProperty)| Measurement Property|An identifiable and observable characteristic of a sensor's observations or ability to make observations| 
| [s3n:Accuracy](https://imergo.com/ns/2015/s3n#Accuracy) | Accuracy |The closeness of agreement between the value of an observation and the true value of the observed quality| | 
| [s3n:Frequency](https://imergo.com/ns/2015/s3n#Frequency) | Frequency |The smallest possible time between one observation and the next| |
| [s3n:Precision](https://imergo.com/ns/2015/s3n#Precision) | Precision |The closeness of agreement between replicate observations on an unchanged or similar quality value| |
| [s3n:Resolution](https://imergo.com/ns/2015/s3n#Resolution) | Resolution |The smallest difference in the value of a quality being observed that would result in perceptably different values of observation results| |
| [s3n:ResponseTime](https://imergo.com/ns/2015/s3n#ResponseTime) | Response Time |The time between a change in the value of an observed quality and a sensor 'settling' on an observed value.| |
| [s3n:Sensitivity](https://imergo.com/ns/2015/s3n#Sensitivity) | Sensitivity |Sensitivity is the quotient of the change in a result of sensor and the corresponding change in a value of a quality being observed| |

### Device {#device}

- **Label**: Device (```https://imergo.com/ns/2015/s3n#Device```)
- **Description**: A device is a physical piece of technology - a system in a
  box. Devices may of course be built of smaller devices and software
  components (i.e. systems have components).
- **Domain of**:
- **Range of**:
- **Related properties**:
-+ dct:title 
-+ dct:description
-+ dct:hasPart

### Sensor {#sensor}

Sensors may be physical devices, computational methods, a laboratory setup with a person following a method, or any other thing that can follow a Sensing Method to observe a Property. 
URI:(https://imergo.com/ns/2015/s3n#Sensor) 

##Observation

An Observation is a Situation in which a Sensing method has been used to estimate or calculate a value of a Property. 

##Condition

Used to specify ranges for qualities that act as conditions on a system/sensor's operation

##ObservationValue

The value of the result of an Observation. An Observation has a result which is the output of some sensor, the result is an information object that encodes some value for a Feature.

##MeasurementCapability

Collects together measurement properties (accuracy, range, precision, etc) and the environmental conditions in which those properties hold, representing a specification of a sensor's capability in those conditions. 

##MeasurementProperty

An identifiable and observable characteristic of a sensor's observations or ability to make observations.

##SensorInput

An Event in the real world that 'triggers' the sensor. 

##SensorOutput

A sensor outputs a piece of information (an observed value), the value itself being represented by an ObservationValue.

##Property

An observable Quality of an Event or Object.

##Accuracy

The closeness of agreement between the value of an observation and the true value of the observed quality.

##Frequency

The smallest possible time between one observation and the next.

##Precision

The closeness of agreement between replicate observations on an unchanged or similar quality value: i.e., a measure of a sensor's ability to consitently reproduce an observation.

##Resolution

The smallest difference in the value of a quality being observed that would result in perceptably different values of observation results.

##ResponseTime

The time between a (step) change inthe value of an observed quality and a sensor (possibly with specified error) 'settling' on an observed value.

##Sensitivity

Sensitivity is the quotient of the change in a result of sensor and the corresponding change in a value of a quality being observed.


# Properties

Class Name | Label | Domain | Range 
:----------: |:-----: |:-----------: |:------------------
| [s3n:detects](https://imergo.com/ns/2015/s3n#detects) | detects | [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor) | [s3n:SensorInput](https://imergo.com/ns/2015/s3n#SensorInput)
| [s3n:observes](https://imergo.com/ns/2015/s3n#observes) | Sensor | [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor) | [s3n:Property](https://imergo.com/ns/2015/s3n#Property)
| [s3n:hasMeasurementCapability](https://imergo.com/ns/2015/s3n#hasMeasurementCapability) | hasMeasurementCapability | [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor) | [s3n:MeasurementCapability](https://imergo.com/ns/2015/s3n#MeasurementCapability) 
| [s3n:observedProperty](https://imergo.com/ns/2015/s3n#observedProperty) | observedProperty | [s3n:Observation](https://imergo.com/ns/2015/s3n#Observation) | [s3n:Property](https://imergo.com/ns/2015/s3n#Property)
| [s3n:observationResult](https://imergo.com/ns/2015/s3n#observationResult) | observationResult | [s3n:Observation](https://imergo.com/ns/2015/s3n#Observation) | [s3n:SensorOutput](https://imergo.com/ns/2015/s3n#Output)
| [s3n:isProducedBy](https://imergo.com/ns/2015/s3n#isProducedBy) | isProducedBy | [s3n:SensorOutput](https://imergo.com/ns/2015/s3n#SensorOutput) | [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor)
| [s3n:observedBy](https://imergo.com/ns/2015/s3n#observedBy) | observedBy | [s3n:Observation](https://imergo.com/ns/2015/s3n#Observation) | [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor) 
| [s3n:hasMeasurementProperty](https://imergo.com/ns/2015/s3n#hasMeasurementProperty) | hasMeasurementProperty | [s3n:MeasurementCapability](https://imergo.com/ns/2015/s3n#MeasurementCapability) | [s3n:MeasurementProperty](https://imergo.com/ns/2015/s3n#MeasurementProperty)
 
##detects

A relation from a sensor to the Stimulus(input) that the sensor can detect.
<br>Domain: [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor)
<br>Range: [s3n:SesorInput](https://imergo.com/ns/2015/s3n#SensorInput)

##observes

Relation between a Sensor and a Property that the sensor can observe.
<br>Domain: [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor)
<br>Range: [s3n:Property](https://imergo.com/ns/2015/s3n#Property)

##hasMeasurementCapability

Relation from a Sensor to a MeasurementCapability describing the measurement properties of the sensor.
<br>Domain: [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor)
<br>Range: [s3n:MeasurementCapability](https://imergo.com/ns/2015/s3n#MeasurementCapability)

##observedProperty

Relation linking an Observation to the Property that was observed.
<br>Domain: [s3n:Observation](https://imergo.com/ns/2015/s3n#Observation)
<br>Range: [s3n:Property](https://imergo.com/ns/2015/s3n#Property)

##observationResult

Relation linking an Observation (i.e., a description of the context, the Situation, in which the observatioin was made) and a Result, which contains a value representing the value associated with the observed Property.
<br>Domain: [s3n:Observation](https://imergo.com/ns/2015/s3n#Observation)
<br>Range: [s3n:SensorOutput](https://imergo.com/ns/2015/s3n#SensorOutput)

##isProducedBy

Relation between a producer and a produced entity: for example, between a sensor and the produced output.
<br>Domain: [s3n:SensorOutput](https://imergo.com/ns/2015/s3n#SensorOutput)
<br>Range: [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor)

##observedBy

Relation between an Observation and Sensor.
<br>Domain: [s3n:Observation](https://imergo.com/ns/2015/s3n#Observayion)
<br>Range: [s3n:Sensor](https://imergo.com/ns/2015/s3n#Sensor)

##hasMeasurementProperty

Relation from a MeasurementCapability to a MeasurementProperty
<br>Domain: [s3n:MeasurementCapability](https://imergo.com/ns/2015/s3n#MeasurementCapability)
<br>Range: [s3n:MeasurementProperty](https://imergo.com/ns/2015/s3n#MeasurementProperty)
