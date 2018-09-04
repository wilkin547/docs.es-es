---
title: Información general sobre la seguridad de SQL Server
ms.date: 03/30/2017
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
ms.openlocfilehash: 25f9f96a550438d242ee409da0d09b7df06de33c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528662"
---
# <a name="overview-of-sql-server-security"></a>Información general sobre la seguridad de SQL Server
Una estrategia de defensa exhaustiva, con niveles superpuestos de seguridad, es la mejor manera de enfrentarse a las amenazas a la seguridad. SQL Server proporciona una arquitectura de seguridad diseñada para permitir a los administradores de bases de datos y desarrolladores crear aplicaciones de base de datos seguras y contrarrestar las amenazas. En cada versión de SQL Server se han introducido mejoras a las versiones anteriores con nuevas características y funcionalidades. No obstante, la seguridad no es una característica integrada más. Cada aplicación tiene requisitos de seguridad propios. Los desarrolladores tienen que saber cuál es la combinación de características y funcionalidades más apropiada para contrarrestar las amenazas conocidas, así como anticiparse a las que puedan ir apareciendo en el futuro.  
  
 Una instancia de SQL Server contiene un conjunto jerárquico de entidades, empezando por el servidor. Cada servidor contiene varias bases de datos y, a su vez, cada base de datos contiene una colección de objetos susceptibles de ser protegidos. Cada elemento protegible de SQL Server tiene asociados *permisos* que se pueden conceder a un *principal*, que es un individuo, grupo o proceso concedido acceso a SQL Server. El marco de seguridad de SQL Server administra el acceso a entidades protegidas mediante *autenticación* y *autorización*.  
  
-   La autenticación es el proceso de inicio de sesión en SQL Server por el que una entidad de seguridad solicita el acceso mediante el envío de credenciales que el servidor evalúa. La autenticación establece la identidad del usuario o proceso que se autentica.  
  
-   La autorización es el proceso con el que se determinan los recursos susceptibles de protegerse a los que tiene acceso una entidad de seguridad, así como las operaciones que les están permitidas a dichos recursos.  
  
 Los temas de esta sección abordan los conceptos básicos de seguridad de SQL Server y proporcionan vínculos a la documentación completa de la versión de los Libros en pantalla de SQL Server que corresponda.  
  
## <a name="in-this-section"></a>En esta sección  
 [Autenticación en SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 Describe los inicios de sesión y autenticación en SQL Server y proporciona vínculos a recursos adicionales.  
  
 [Roles de servidor y base de datos en SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 Describe funciones fijas de bases de datos y servidores, funciones de base de datos personalizadas y cuentas integradas, y proporciona vínculos a recursos adicionales.  
  
 [Propiedad y separación de esquemas de usuario en SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 Describe la propiedad de los objetos y separación entre usuario y esquema, y proporciona vínculos a recursos adicionales.  
  
 [Autorización y permisos en SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 Describe la concesión de permisos a través del principio de los privilegios mínimos y proporciona vínculos a recursos adicionales.  
  
 [Cifrado de datos en SQL Server](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 Describe las opciones de cifrado de datos en SQL Server y proporciona vínculos a recursos adicionales.  
  
 [Seguridad de integración de CLR en SQL Server](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 Proporciona vínculos a recursos de seguridad de la integración CLR.  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
