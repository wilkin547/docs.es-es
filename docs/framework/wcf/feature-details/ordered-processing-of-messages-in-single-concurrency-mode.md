---
title: "Procesamiento de mensajes por orden en modo de simultaneidad &#250;nica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Procesamiento de mensajes por orden en modo de simultaneidad &#250;nica
WCF no garantiza el orden en que se procesan los mensajes, a menos que el canal subyacente sea con sesión. Por ejemplo, un servicio de WCF que usa MsmqInputChannel, que no es un canal con sesión, no podrá procesar mensajes en orden. Hay algunos casos donde un desarrollador puede desear el comportamiento de procesamiento por orden pero no desee usar sesiones.En este tema se describe cómo configurar este comportamiento cuando un servicio se ejecuta en modo de simultaneidad única.  
  
## Procesamiento de mensajes en orden  
 Se ha agregado un nuevo atributo denominado <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> a <xref:System.ServiceModel.ServiceBehaviorAttribute>.Cuando <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> se establece en true y <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en <xref:System.ServiceModel.ConcurrencyMode>, los mensajes enviados al servicio se procesará en orden.El fragmento de código siguiente muestra cómo establecer estos atributos.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
  
```  
  
 Si <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en cualquier otro valor, se produce <xref:System.InvalidOperationException>.  
  
## Vea también  
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [Simultaneidad](../../../../docs/framework/wcf/samples/concurrency.md)