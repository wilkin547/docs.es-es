---
title: "Reliability | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SQL Server [.NET Framework]"
  - "managed code, reliability"
  - "reliability [.NET Framework]"
  - "writing reliable code"
  - "code, reliability"
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Reliability
Es importante que el código que se ejecute en entornos de servidor como SQL Server esté protegido contra las excepciones asincrónicas.  La confiabilidad, tal y como se describe aquí, no es específica de SQL Server sino que también se aplica a la escritura de código confiable para cualquier host que se ejecute en un entorno de la versión 2.0 de .NET Framework.  Sin embargo, SQL Server es el primer servicio que realiza un uso extensivo de las nuevas características de confiabilidad de la versión 2.0, por lo que es objeto de este ejemplo.  
  
 El código que se ejecuta en SQL Server debe tratarse con unas pautas de confiabilidad más estrictas que las de otros entornos de servidor.  Esto es debido a la operación continua de SQL Server en el borde del consumo de recursos.  <xref:System.OutOfMemoryException> y excepciones de <xref:System.Threading.ThreadAbortException> no son infrecuentes en el entorno de SQL Server.  En general, estas directrices están menos centradas en la confiabilidad y más en permitir que el código administrado de confianza plena pueda fallar sin más problemas ante el reciclaje del nivel de <xref:System.AppDomain>, que es la forma principal que usa el servidor para mantener la consistencia y la disponibilidad.  
  
## En esta sección  
 [SQL Server Programming and Host Protection Attributes](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 Describe cómo utiliza SQL Server el atributo <xref:System.Security.Permissions.HostProtectionAttribute> para restringir la ejecución de código administrado.  
  
 [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md)  
 Proporciona instrucciones para escribir código que cumple los requisitos de confiabilidad.  
  
 [Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)  
 Describe la función y el comportamiento de áreas de ejecución restringida \(CER\).  
  
## Referencia  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>