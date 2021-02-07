---
description: Más información acerca de cómo proteger aplicaciones ADO.NET
title: Proteger aplicaciones
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 4e4d219d1f4249846943d019e174abd6d43687c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718881"
---
# <a name="securing-adonet-applications"></a>Protección de aplicaciones de ADO.NET

Para escribir una aplicación de ADO.NET segura es necesario algo más que evitar los errores de codificación más comunes, como no validar los datos proporcionados por el usuario. Una aplicación que tiene acceso a los datos tiene muchos puntos de error potenciales que un atacante puede aprovechar para recuperar, manipular o destruir información confidencial. Por eso es importante comprender todos los aspectos de la seguridad, desde el proceso de modelo de amenazas durante la fase de diseño de su aplicación hasta la implementación y el posterior mantenimiento.  
  
.NET Framework ofrece muchas clases, servicios y herramientas que resultan muy útiles para proteger y administrar aplicaciones de base de datos. Common Language Runtime (CLR) proporciona un entorno de seguridad de tipos en el que ejecutar el código, junto con la seguridad de acceso del código (CAS) para restringir aún más los permisos del código administrado. Si se siguen las recomendaciones de codificación del acceso seguro a datos, se reduce el daño que podría provocar un posible agresor.  
  
El código seguro no protege de la vulnerabilidad de seguridad que provoca el propio usuario cuando trabaja con recursos no administrados como bases de datos. La mayoría de las bases de datos, como SQL Server, tienen sus propios sistemas de seguridad, que contribuyen a mejorarla cuando se implementan correctamente. Sin embargo, incluso un origen de datos con un robusto sistema de seguridad puede sufrir un ataque si no se ha configurado correctamente.  
  
## <a name="in-this-section"></a>En esta sección

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

 [Guía de seguridad de DataSet y DataTable](dataset-datatable-dataview/security-guidance.md)  
 Proporciona instrucciones de seguridad para <xref:System.Data.DataSet> y <xref:System.Data.DataTable> .

 [Seguridad de SQL Server](./sql/sql-server-security.md)  
 Describe las características de seguridad de SQL Server desde la perspectiva del desarrollador.  
  
 [Consideraciones sobre la seguridad](./ef/security-considerations.md)  
 Describe la seguridad de las aplicaciones de Entity Framework.  
  
 [Seguridad](../../../standard/security/index.md)  
 Contiene vínculos a artículos en los que se describen todos los aspectos de seguridad de .NET.  
  
 [Herramientas de seguridad](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))  
 Herramientas de .NET Framework para proteger y administrar las directivas de seguridad.  
  
 [Recursos para crear aplicaciones seguras](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))  
 Proporciona vínculos a artículos para crear aplicaciones seguras.  
  
 [Bibliografía sobre seguridad](/visualstudio/ide/securing-applications)  
 Proporciona vínculos a recursos externos disponibles en línea e impresos.  
  
## <a name="see-also"></a>Vea también

- [ADO.NET](index.md)
- [Información general de ADO.NET](ado-net-overview.md)
