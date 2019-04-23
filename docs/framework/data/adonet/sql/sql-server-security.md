---
title: Seguridad de SQL Server
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: 4aa4feadb6305f8a0ea6f99c2add780d6fca95cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080777"
---
# <a name="sql-server-security"></a>Seguridad de SQL Server
SQL Server incluye diferentes características que admiten la creación de aplicaciones de base de datos seguras.  
  
 Las consideraciones comunes de seguridad, como el robo de datos o el vandalismo, se aplican independientemente de la versión de SQL Server que se utilice. La integridad de los datos también se debe considerar como un problema de seguridad. Si los datos no están protegidos, es posible que acaben perdiendo su valor si se permite la manipulación de datos ad hot y los datos se modifican sin intención o de forma malintencionada con valores incorrectos o bien se eliminan por completo. Además, a menudo existen requisitos legales que se deben cumplir, como el almacenamiento correcto de información confidencial. El almacenamiento de determinados tipos de datos personales está totalmente prohibido, en función de las leyes que se apliquen en una jurisdicción determinada.  
  
 Cada versión de SQL Server incluye diferentes características de seguridad, al igual que cada versión de Windows, y las versiones posteriores cuentan con funcionalidad mejorada con respecto a las anteriores. Es importante comprender que las características de seguridad no pueden garantizar por sí solas una aplicación de base de datos segura. Cada aplicación de base de datos es única en lo que respecta a los requisitos, el entorno de ejecución, el modelo de implementación, la ubicación física y el rellenado por parte del usuario. Algunas aplicaciones que son locales en cuanto al ámbito pueden necesitar una seguridad mínima, en tanto que otras aplicaciones locales o las aplicaciones implementadas en Internet pueden precisar medidas estrictas de seguridad y supervisión y evaluación continuas.  
  
 Los requisitos de seguridad de una aplicación de base de datos de SQL Server se deben tener en cuenta en tiempo de diseño, no a posteriori. La evaluación de las amenazas en las primeras fases del ciclo de desarrollo permite reducir al mínimo los posibles daños cuando se detecte una vulnerabilidad.  
  
 Sin embargo, a pesar de que el diseño inicial de la aplicación resulte adecuado, pueden surgir nuevas amenazas a medida que evoluciona el sistema. La creación de varias líneas de defensa en torno a la base de datos permite reducir al mínimo los daños producidos por una infracción de seguridad. La primera línea de defensa consiste en reducir el área de ataque; para ello, no se deben conceder más permisos que los estrictamente necesarios.  
  
 Los temas de esta sección describen brevemente las características de seguridad de SQL Server de interés para los programadores, con vínculos a temas relevantes en los Libros en pantalla de SQL Server y otros recursos que proporcionan información más detallada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 Describe la arquitectura y las características de seguridad de SQL Server.  
  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 Contiene temas que describen diferentes escenarios de seguridad de aplicaciones para aplicaciones de ADO.NET y SQL Server.  
  
 [Seguridad de SQL Server Express](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 Describe las consideraciones de seguridad para SQL Server Express.  
  
## <a name="related-sections"></a>Secciones relacionadas  
[Centro de seguridad para el motor de base de datos SQL Server y Azure SQL Database](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
Describe las consideraciones de seguridad para SQL Server y Azure SQL Database.

[Consideraciones de seguridad para una instalación de SQL Server](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
Se describen cuestiones de seguridad a tener en cuenta antes de instalar SQL Server.

## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
