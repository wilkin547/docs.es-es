---
title: "ServiceBehaviorAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## Sintaxis  
  
```  
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## Métodos  
 La clase ServiceBehaviorAttribute no define ningún método.  
  
## Propiedades  
 La clase ServiceBehaviorAttribute tiene las propiedades siguientes:  
  
### AutomaticSessionShutdown  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si cerrar automáticamente una sesión cuando un cliente cierra una sesión de salida.  
  
### ConcurrencyMode  
 Tipo de datos: cadena  
Tipo de acceso: solo lectura  
  
 Indica si un servicio admite un subproceso, varios subprocesos o las llamadas reentrantes.  
  
### ConfigurationName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de la configuración del servicio.  
  
### IgnoreExtensionDataObject  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si enviar datos de la serialización desconocidos hacia la conexión.  
  
### IncludeExceptionDetailInFaults  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.  
  
### InstanceContextMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica cuándo se crea un nuevo objeto de servicio.  
  
### MaxItemsInObjectGraph  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de elementos permitido en un objeto serializado.  
  
### Nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El atributo de nombre del servicio en WSDL.  
  
### Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El espacio de nombres de destino del servicio en WSDL.  
  
### ReleaseServiceInstanceOnTransactionComplete  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el objeto de servicio se recicla cuando la transacción actual completa.  
  
### TransactionAutoCompleteOnSessionClose  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si las transacciones pendientes se completan cuando la sesión actual se cierra.  
  
### TransactionIsolationLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica el nivel de aislamiento de la transacción.  
  
### TransactionTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El período dentro del que una transacción se debe completar.  
  
### UseSynchronizationContext  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si utilizar el contexto de sincronización actual para elegir la ejecución del subproceso.  
  
### ValidateMustUnderstand  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>