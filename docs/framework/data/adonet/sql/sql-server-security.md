---
title: Seguridad de SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: "8"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: abb7c9322a9b7ddfd3e0add4d8b9be6941c5e240
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="sql-server-security"></a>Seguridad de SQL Server
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] incluye muchas características que admiten la creación de aplicaciones de base de datos seguras.  
  
 Las consideraciones comunes de seguridad, como el robo de datos o el vandalismo, se aplican independientemente de la versión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] que se use. La integridad de los datos también se debe considerar como un problema de seguridad. Si los datos no están protegidos, es posible que acaben perdiendo su valor si se permite la manipulación de datos ad hot y los datos se modifican sin intención o de forma malintencionada con valores incorrectos o bien se eliminan por completo. Además, a menudo existen requisitos legales que se deben cumplir, como el almacenamiento correcto de información confidencial. El almacenamiento de determinados tipos de datos personales está totalmente prohibido, en función de las leyes que se apliquen en una jurisdicción determinada.  
  
 Cada versión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] incluye diferentes características de seguridad, del mismo modo que las versiones de Windows más recientes mejoran la funcionalidad respecto a las anteriores. Es importante comprender que las características de seguridad no pueden garantizar por sí solas una aplicación de base de datos segura. Cada aplicación de base de datos es única en lo que respecta a los requisitos, el entorno de ejecución, el modelo de implementación, la ubicación física y el rellenado por parte del usuario. Algunas aplicaciones que son locales en cuanto al ámbito pueden necesitar una seguridad mínima, en tanto que otras aplicaciones locales o las aplicaciones implementadas en Internet pueden precisar medidas estrictas de seguridad y supervisión y evaluación continuas.  
  
 Los requisitos de seguridad de una aplicación de base de datos de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] se deben tener en cuenta en el tiempo de diseño, no a posteriori. La evaluación de las amenazas en las primeras fases del ciclo de desarrollo permite reducir al mínimo los posibles daños cuando se detecte una vulnerabilidad.  
  
 Sin embargo, a pesar de que el diseño inicial de la aplicación resulte adecuado, pueden surgir nuevas amenazas a medida que evoluciona el sistema. La creación de varias líneas de defensa en torno a la base de datos permite reducir al mínimo los daños producidos por una infracción de seguridad. La primera línea de defensa consiste en reducir el área de ataque; para ello, no se deben conceder más permisos que los estrictamente necesarios.  
  
 Los temas de esta sección describen brevemente las características de seguridad en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] de interés para los desarrolladores, con vínculos a temas relevantes en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] y otros recursos que proporcionan cobertura más detallada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 Describe la arquitectura y las características de seguridad de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 Contiene temas que describen diferentes escenarios de seguridad de aplicaciones para aplicaciones de ADO.NET y [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Seguridad de SQL Server Express](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 Describe cuestiones de seguridad relacionadas con [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Seguridad y protección (motor de base de datos)](http://msdn2.microsoft.com/library/bb510589\(SQL.100\).aspx.)  
 Temas de seguridad de los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Consideraciones de seguridad para SQL Server](http://go.microsoft.com/fwlink/?LinkId=98587)  
 Temas de seguridad de los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
