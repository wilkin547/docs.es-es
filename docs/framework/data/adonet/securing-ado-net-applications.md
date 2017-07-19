---
title: "Proteger aplicaciones de ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Proteger aplicaciones de ADO.NET
Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario.  Una aplicación que tiene acceso a datos tiene muchos puntos débiles potenciales que un agresor puede aprovechar para obtener, manipular o destruir datos confidenciales.  Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.  
  
 .NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos.  Common Language Runtime \(CLR\) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código \(CAS\) para restringir aún más los permisos del código administrado.  Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.  
  
 El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos.  La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente.  Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.  
  
## En esta sección  
 [Información general de seguridad](../../../../docs/framework/data/adonet/security-overview.md)  
 Proporciona recomendaciones para diseñar aplicaciones seguras de ADO.NET.  
  
 [Acceso seguro a datos](../../../../docs/framework/data/adonet/secure-data-access.md)  
 Describe cómo trabajar con datos de un origen de datos protegido.  
  
 [Aplicaciones cliente seguras](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 Describe consideraciones de seguridad para aplicaciones cliente.  
  
 [Seguridad de acceso del código y ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)  
 Describe cómo se puede proteger el código de ADO.NET mediante la seguridad de acceso del código.  También explica cómo trabajar con confianza parcial.  
  
 [Privacidad y seguridad de datos](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 Describe las opciones de cifrado para las aplicaciones de ADO.NET.  
  
## Secciones relacionadas  
 [Seguridad en SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.  
  
 [Consideraciones de seguridad](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 Describe la seguridad de las aplicaciones de Entity Framework.  
  
 [Security](../../../../docs/standard/security/index.md)  
 Contiene vínculos a temas en los que se describen todos los aspectos de la seguridad en .NET Framework.  
  
 [Security Tools](http://msdn.microsoft.com/es-es/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.  
  
 [Resources for Creating Secure Applications](http://msdn.microsoft.com/es-es/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 Proporciona vínculos a temas para crear aplicaciones seguras.  
  
 [Bibliografía sobre seguridad](../Topic/Security%20Bibliography.md)  
 Proporciona vínculos a recursos externos disponibles en línea e impresos.  
  
## Vea también  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)