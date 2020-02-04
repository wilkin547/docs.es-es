---
title: Proteger aplicaciones
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: c1bdf4329665e4d29a47c26fb7dba8eb41c1cc3a
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980033"
---
# <a name="securing-adonet-applications"></a>Proteger aplicaciones de ADO.NET
Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario. Una aplicación que tiene acceso a datos tiene muchos puntos débiles potenciales que un agresor puede aprovechar para obtener, manipular o destruir datos confidenciales. Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.  
  
 .NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos. Common Language Runtime (CLR) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código (CAS) para restringir aún más los permisos del código administrado. Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.  
  
 El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos. La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente. Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.  
  
## <a name="in-this-section"></a>Esta sección  
 [Información general sobre seguridad](security-overview.md)  
 Proporciona recomendaciones para diseñar aplicaciones seguras de ADO.NET.  
  
 [Acceso seguro a datos](secure-data-access.md)  
 Describe cómo trabajar con datos de un origen de datos protegido.  
  
 [Aplicaciones cliente seguras](secure-client-applications.md)  
 Describe consideraciones de seguridad para aplicaciones cliente.  
  
 [Seguridad de acceso del código y ADO.NET](code-access-security.md)  
 Describe cómo se puede proteger el código de ADO.NET mediante la seguridad de acceso del código. También explica cómo trabajar con confianza parcial.  
  
 [Privacidad y seguridad de datos](privacy-and-data-security.md)  
 Describe las opciones de cifrado para las aplicaciones de ADO.NET.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Seguridad de SQL Server](./sql/sql-server-security.md)  
 Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.  
  
 [Consideraciones de seguridad](./ef/security-considerations.md)  
 Describe la seguridad de las aplicaciones de Entity Framework.  
  
 [Seguridad](../../../standard/security/index.md)  
 Contiene vínculos a temas en los que describen todos los aspectos de la seguridad en .NET.  
  
 [Herramientas de seguridad](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))  
 Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.  
  
 [Recursos para crear aplicaciones seguras](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))  
 Proporciona vínculos a temas para crear aplicaciones seguras.  
  
 [Bibliografía sobre seguridad](/visualstudio/ide/securing-applications)  
 Proporciona vínculos a recursos externos disponibles en línea e impresos.  
  
## <a name="see-also"></a>Vea también

- [ADO.NET](index.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
