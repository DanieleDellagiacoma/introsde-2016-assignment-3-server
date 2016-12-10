# introsde-2016-assignment-3-server

## SERVER
The server is divided in the following packages and classes:

* introsde.document.dao
  * LifeCoachDao.java
* introsde.document.endpoint
  * PeoplePublisher.java
* introsde.document.model
  * HealthMeasureHistory.java
  * HealthProfile.java
  * MeasureDefinition.java
  * Person.java
* introsde.document.ws
  * People.java
  * PeopleImpl.java
  
 
The model supported by the service includes:
```java
public class Person {
 int idPerson;
 String firstname;
 String lastname;
 Date birthdate
 HealthProfile healthprofile;
}
public class HealthProfile {
 int idMeasure,
 MeasureDefinition idMeasureDef;
 String idPerson;
 String value;
}
public class HealthMeasureHistory {
 int idMeasureHistory,
 String idPerson;
 String value;
 Date timestamp;
 MeasureDefinition idMeasureDef;
}
public class MeasureDefinition {
 int idMeasureDef,
 String measureName;
 String measureType;
}
```

## DEPLOYMENT

The server was deployed on Heroku in the following way (starting from the root folder of the project):

```sh
$ git init

$ git add .

$ git commit -m "first commit"

$ heroku create --stack cedar --buildpack https://github.com/DanieleDellagiacoma/heroku-buildpack-ant

$ git push heroku master
```
