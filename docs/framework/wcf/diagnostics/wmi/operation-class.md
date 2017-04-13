---
title: "Clase de operaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Clase de operaci&#243;n
Operación  
  
## Sintaxis  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## Métodos  
 La clase Operación no define ningún método.  
  
## Propiedades  
 La clase Operación tiene las siguientes propiedades:  
  
### Acción  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La acción WS\-Addressing del mensaje de solicitud.  
  
### AsyncPattern  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica que una operación se implementa de forma asincrónica mediante `Begin` \[abrir\/cerrar corchetes angulares\] y `End` \[abrir\/cerrar corchetes angulares\] el par de método en un contrato de servicios.  
  
### Comportamientos  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a esta operación.  
  
### IsCallback  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Verdadero cuando la operación es una operación de devolución de llamada.  
  
### IsInitiating  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si el método implementa una operación que puede iniciar una sesión en el servidor.  
  
### IsOneWay  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si una operación devuelve un mensaje de respuesta.  
  
### IsTerminating  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si una operación devuelve un mensaje de respuesta.  
  
### MethodSignature  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La firma del método de la operación.  
  
### Nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de la operación.  
  
### ParameterTypes  
 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Tipos de los parámetros de la operación.  
  
### ReplyAction  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El valor de la acción SOAP para el mensaje de respuesta de la operación.  
  
### ReturnType  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Tipo devuelto de la operación.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Description.OperationDescription>