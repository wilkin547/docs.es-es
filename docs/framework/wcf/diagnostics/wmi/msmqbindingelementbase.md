---
title: "MsmqBindingElementBase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# MsmqBindingElementBase
MsmqBindingElementBase  
  
## Sintaxis  
  
```  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## Métodos  
 La clase TraceListenerArgument no define ningún método.  
  
## Propiedades  
 La clase MsmqBindingElementBase tiene las siguientes propiedades:  
  
### CustomDeadLetterQueue  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un URI que contiene la ubicación de la cola de mensajes no enviados de cada aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o envío han fallado.  
  
### DeadLetterQueue  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor de enumeración que indica el tipo de cola de mensajes no enviados que se ha de usar.  
  
### Durable  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si los mensajes procesados por este enlace son duraderos o volátiles.  
  
### ExactlyOnce  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que indica si los mensajes procesados por este enlace se reciben solo una vez.  
  
### MaxRetryCycles  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de ciclos de reintento de entrega de mensajes a la aplicación receptora.  
  
### ReceiveErrorHandling  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Los valores para el control de mensajes dudosos.  
  
### ReceiveRetryCount  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de intentos de reintento inmediato en un mensaje que se lee desde la cola de la aplicación.  
  
### RetryCycleDelay  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica el tiempo de retardo entre los ciclos de reintento al intentar entregar un mensaje que no se pudo entregar inmediatamente.  
  
### TimeToLive  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo que indica cuánto tiempo pueden estar en la cola los mensajes procesados por este enlace antes de expirar.  
  
### UseMsmqTracing  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que indica si los mensajes procesados por este enlace se deberían seguir paso a paso.  
  
### UseSourceJournal  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que indica si las copias de mensajes procesados por este enlace deberían almacenarse en la cola de diario de origen.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.NetMsmqBinding>   
 <xref:System.ServiceModel.MsmqBindingBase>