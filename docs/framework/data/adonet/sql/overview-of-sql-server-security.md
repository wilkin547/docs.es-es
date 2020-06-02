---
title: Información general sobre la seguridad de SQL Server
description: Obtenga información acerca de la arquitectura de seguridad de SQL Server para saber qué características y funcionalidad contrarrestan las amenazas conocidas y para anticiparse a las amenazas futuras.
ms.date: 03/30/2017
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
ms.openlocfilehash: c423a408e607c51c048ad08b91122a1fe06e31b2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286280"
---
# <a name="overview-of-sql-server-security"></a>Información general sobre la seguridad de SQL Server
Una estrategia de defensa exhaustiva, con niveles superpuestos de seguridad, es la mejor manera de enfrentarse a las amenazas a la seguridad. SQL Server proporciona una arquitectura de seguridad diseñada para permitir a los administradores de bases de datos y desarrolladores crear aplicaciones de base de datos seguras y contrarrestar las amenazas. En cada versión de SQL Server se han introducido mejoras a las versiones anteriores con nuevas características y funcionalidades. No obstante, la seguridad no es una característica integrada más. Cada aplicación tiene requisitos de seguridad propios. Los desarrolladores tienen que saber cuál es la combinación de características y funcionalidades más apropiada para contrarrestar las amenazas conocidas, así como anticiparse a las que puedan ir apareciendo en el futuro.  
  
 Una instancia de SQL Server contiene un conjunto jerárquico de entidades, empezando por el servidor. Cada servidor contiene varias bases de datos y, a su vez, cada base de datos contiene un conjunto de objetos susceptibles de ser protegidos. Cada SQL Server protegible tiene *permisos* asociados que se pueden conceder a una *entidad*de seguridad, que es una persona, grupo o proceso al que se concede acceso a SQL Server. El marco de seguridad de SQL Server administra el acceso a las entidades protegibles a través de la *autenticación* y la *autorización*.  
  
- La autenticación es el proceso de inicio de sesión en SQL Server por el que una entidad de seguridad solicita el acceso mediante el envío de credenciales que el servidor evalúa. La autenticación establece la identidad del usuario o proceso que se autentica.  
  
- La autorización es el proceso en el que se determinan los recursos protegibles a los que puede obtener acceso una entidad de seguridad y las operaciones permitidas para dichos recursos.  
  
 Los temas de esta sección abordan los conceptos básicos de seguridad de SQL Server y proporcionan vínculos a la documentación completa de la versión de los Libros en pantalla de SQL Server que corresponda.  
  
## <a name="in-this-section"></a>En esta sección  
 [Autenticación en SQL Server](authentication-in-sql-server.md)  
 Describe los inicios de sesión y la autenticación en SQL Server y proporciona vínculos a recursos adicionales.  
  
 [Roles de servidor y base de datos en SQL Server](server-and-database-roles-in-sql-server.md)  
 Describe funciones fijas de bases de datos y servidores, funciones de base de datos personalizadas y cuentas integradas, y proporciona vínculos a recursos adicionales.  
  
 [Propiedad y separación de esquemas de usuario en SQL Server](ownership-and-user-schema-separation-in-sql-server.md)  
 Describe la propiedad de los objetos y separación entre usuario y esquema, y proporciona vínculos a recursos adicionales.  
  
 [Autorización y permisos en SQL Server](authorization-and-permissions-in-sql-server.md)  
 Describe la concesión de permisos a través del principio de los privilegios mínimos y proporciona vínculos a recursos adicionales.  
  
 [Cifrado de datos en SQL Server](data-encryption-in-sql-server.md)  
 Describe las opciones de cifrado de datos en SQL Server y proporciona vínculos a recursos adicionales.  
  
 [Seguridad de integración de CLR en SQL Server](clr-integration-security-in-sql-server.md)  
 Proporciona vínculos a recursos de seguridad de la integración CLR.  
  
## <a name="see-also"></a>Consulte también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Seguridad de SQL Server](sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
