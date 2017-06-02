---
title: "CallbackBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# CallbackBehavior
CallbackBehavior  
  
## Sintaxis  
  
```  
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## Métodos  
 La clase CallbackBehavior no define ningún método.  
  
## Propiedades  
 La clase CallbackBehavior tiene las propiedades siguientes:  
  
### AutomaticSessionShutdown  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.  
  
### ConcurrencyMode  
 Tipo de datos: cadena  
Tipo de acceso: solo lectura  
  
 Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.  
  
### IgnoreExtensionDataObject  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.  
  
### IncludeExceptionDetailInFaults  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.  
  
### MaxItemsInObjectGraph  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de elementos permitido en un objeto serializado.  
  
### UseSynchronizationContext  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.  
  
### ValidateMustUnderstand  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>