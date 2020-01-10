---
title: Confiabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
ms.openlocfilehash: 2d6601c4cbad32f768ff16301307083f35d986a0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715965"
---
# <a name="reliability"></a>Confiabilidad
Es importante que el código que se ejecuta en entornos de servidor, como SQL Server, proteja contra las excepciones asincrónicas. Como ya se ha dicho, la confiabilidad no es específica de SQL Server, sino de la escritura de código confiable para cualquier host que se ejecute en un entorno de .NET Framework versión 2.0. Pero SQL Server es el primer servicio que realiza un amplio uso de las nuevas características de confiabilidad de la versión 2.0, razón por la que se usa como ejemplo.  
  
 El código que se ejecuta en SQL Server debe tratar con directrices de confiabilidad más estrictas que otros entornos de servidor. Esto se debe a que SQL Server siempre funciona en el límite del consumo de recursos.  No es raro que se produzcan excepciones <xref:System.OutOfMemoryException> y <xref:System.Threading.ThreadAbortException> en el entorno de SQL Server. En general, estas instrucciones se centran menos en la confiabilidad y más en permitir que el código administrado de plena confianza genere un error ante un reciclaje de nivel <xref:System.AppDomain>, que es la principal manera que tiene el servidor de mantener la coherencia y la disponibilidad.  
  
## <a name="in-this-section"></a>Esta sección  
 [Programación en SQL Server y atributos de protección de host](sql-server-programming-and-host-protection-attributes.md)  
 Describe la manera en que SQL Server usa el atributo <xref:System.Security.Permissions.HostProtectionAttribute> para restringir la ejecución de código administrado.  
  
 [Reliability Best Practices (Procedimientos recomendados para la confiabilidad)](reliability-best-practices.md)  
 Proporciona instrucciones para escribir código que cumpla los requisitos de confiabilidad.  
  
 [Regiones de ejecución restringidas](constrained-execution-regions.md)  
 Describe el funcionamiento y el comportamiento de las regiones de ejecución restringidas (CER).  
  
## <a name="reference"></a>Referencia  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
