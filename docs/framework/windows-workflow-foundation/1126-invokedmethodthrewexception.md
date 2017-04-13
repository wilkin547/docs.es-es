---
title: "1126 - InvokedMethodThrewException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1126 - InvokedMethodThrewException
## Propiedades  
  
|||  
|-|-|  
|Id.|1126|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Descripción  
 Indica que se produjo una excepción en el método invocado por la actividad InvokeMethod.  
  
## Mensaje  
 Se produjo una excepción en el método invocado por la actividad '%1'  %2  
  
## Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|----------------------------------|--------------------------------|-----------------|  
|InvokeMethod|xs:string|Identificación y nombre para mostrar de la actividad InvokeMethod.|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|