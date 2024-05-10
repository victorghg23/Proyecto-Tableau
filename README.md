# _**PROYECTO TABLEAU: ALIANZAS INTERNACIONALES**_ 🪖🎖️

## Estado del Proyecto

Proyecto Final del segundo modulo de Ironhack

## Objetivo del Proyecto

El objetivo del proyecto consiste en conseguir llevar a cabo la representación de diferentes datos correlacionados entre sí en diferentes tablas en formato .csv, donde se pretende alcanzar el suficiente conocimiento para conocer los datos de las principales alianzas a nivel internacional, sus operaciones y su posición geográfica.

## Lenguajes de Programación Principales

Única y exclusivamente he hecho uso de python para representar los dataframe necesarios, y así poder alcanzar a conocer la relación entre tablas, y una vez cumplido este punto, añadir los archivos .csv en la fuente de datos de Tableau para así poder comenzar su representación.

Para conocer la correlación entre tablas, adjunto el siguiente código que deberá ser copiado en la web de [DbDiagram](https://dbdiagram.io/home):

'''
Table countries as C {
  CountryID int [pk]
  CountryName varchar
  Region varchar
  Note: 'Stores information about countries'
}

Table agencies as A {
  AgencyID int [pk]
  AgencyName varchar
  CountryID int [ref: > C.CountryID]
  Note: 'Security agencies per country'
}

Table personnel as P {
  PersonnelID int [pk]
  Name varchar
  AgencyID int [ref: > A.AgencyID]
  Position varchar
  ClearanceLevel varchar
  Note: 'People working in security agencies'
}

Table operations as O {
  OperationID int [pk]
  OperationName varchar
  CountryID int [ref: > C.CountryID]
  AgencyID int [ref: > A.AgencyID]
  TechID int [ref: > Tech.TechID]
  StartDate date
  EndDate date
  Note: 'Security operations conducted by agencies'
}

Table threats as T {
  ThreatID int [pk]
  ThreatType varchar
  Description varchar
  Note: 'Types of security threats identified'
}

Table threat_reports as TR {
  ReportID int [pk]
  ThreatID int [ref: > T.ThreatID]
  OperationID int [ref: > O.OperationID]
  ReportDate date
  Details text
  Note: 'Reports on specific threats during operations'
}

Table intelligence as I {
  IntelID int [pk]
  OperationID int [ref: > O.OperationID]
  Details text
  DateGathered date
  Note: 'Intelligence data gathered from operations'
}

Table technology as Tech {
  TechID int [pk]
  TechName varchar
  TechType varchar
  Note: 'Technology used in security operations'
}

Table events as E {
  EventID int [pk]
  EventName text
  CountryID int [ref: > C.CountryID]
  Date date
  Note: 'Security events and incidents'
}

Table alliances as AL {
  AllianceID int [pk]
  AllianceName varchar
  Note: 'International security alliances'
}

Table alliance_memberships as AM {
  AllianceID int [ref: > AL.AllianceID]
  CountryID int [ref: > C.CountryID]
  Note: 'Memberships of countries in security alliances'}
'''
