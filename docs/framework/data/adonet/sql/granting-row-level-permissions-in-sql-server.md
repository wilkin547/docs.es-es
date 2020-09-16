---
title: Conceder permisos de nivel de fila en SQL Server
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: 0b34eaee4b66a2be82049816f0a98b9f53012303
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554858"
---
# <a name="granting-row-level-permissions-in-sql-server"></a>Conceder permisos de nivel de fila en SQL Server

En algunos casos, existe un requisito para controlar el acceso a los datos a un nivel más detallado que el que se deriva simplemente de conceder, revocar o denegar permisos. Por ejemplo, una aplicación de bases de datos de hospital puede requerir que se restrinja el acceso a los médicos individuales solo a la información relacionada con sus pacientes. Requisitos similares se producen en muchos ámbitos, como en aplicaciones financieras, legales, gubernamentales y militares. Para ayudar a resolver estos escenarios, SQL Server 2016 ofrece una característica de [seguridad por filas](/sql/relational-databases/security/row-level-security) que simplifica y centraliza la lógica de acceso por filas en una directiva de seguridad. Para las versiones anteriores de SQL Server, se puede lograr una funcionalidad similar con vistas para aplicar el filtrado por filas.

## <a name="implementing-row-level-filtering"></a>Implementación de filtros por filas

El filtrado por filas se usa para la información de almacenamiento de aplicaciones en una tabla única como en el ejemplo anterior del hospital. Para implementar el filtrado por filas, cada fila tiene una columna que define un parámetro diferenciador, como un nombre de usuario, una etiqueta u otro identificador. Para crear una vista o una directiva de seguridad en la tabla, que filtre las filas a las que puede tener acceso el usuario. Después, cree procedimientos almacenados parametrizados, que controlan los tipos de consultas que el usuario puede ejecutar.

En el siguiente ejemplo se describe cómo configurar el filtrado por filas basándose en un usuario o nombre de inicio de sesión:

- Crear la tabla agregando una columna para almacenar el nombre.

- Habilite el filtrado por filas:

  - Si usa SQL Server 2016 o posterior, o la [Base de datos SQL de Azure](/azure/sql-database/), cree una directiva de seguridad que agregue un predicado en la tabla restringiendo las filas devueltas a aquellas que coinciden con el usuario de base de datos actual (mediante la función integrada CURRENT_USER()) o el nombre de inicio de sesión actual (mediante la función integrada de SUSER_SNAME()):

      ```sql
      CREATE SCHEMA Security
      GO

      CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)
          RETURNS TABLE
          WITH SCHEMABINDING
      AS
          RETURN SELECT 1 AS accessResult
          WHERE @UserName = SUSER_SNAME()
      GO

      CREATE SECURITY POLICY Security.userAccessPolicy
          ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,
          ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable
      GO
      ```

  - Si usa una versión de SQL Server anterior a 2016, puede lograr una funcionalidad similar con una vista:

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- Cree procedimientos almacenados para seleccionar, insertar, actualizar y eliminar datos. Si el filtrado está aplicado por una directiva de seguridad, los procedimientos almacenados deben llevar a cabo estas operaciones en la tabla base directamente; de lo contrario, si el filtrado está aplicado por una vista, los procedimientos almacenados deben funcionar en su lugar con la vista. La directiva de seguridad o la vista filtrarán automáticamente las filas devueltas o modificadas por las consultas de usuario, y el procedimiento almacenado ofrecerá un mayor límite de seguridad para impedir que los usuarios con acceso directo a consultas ejecuten correctamente las consultas que pueden inferir la existencia de datos filtrados.

- Para los procedimientos almacenados que insertan datos, capture el nombre de usuario utilizando el mismo rol especificado en la vista o directiva de seguridad e inserte dicho valor en la columna UserName.

- Denegar todos los permisos en las tablas (y vistas, si es aplicable) al rol `public` . Los usuarios no podrán heredar permisos de otros roles de base de datos porque el predicado de filtro se basa en nombres de inicio de sesión o usuarios, no en roles.

- Conceder permisos EXECUTE en los procedimientos almacenados a roles de bases de datos. Los usuarios sólo pueden obtener acceso a datos a través de los procedimientos almacenados proporcionados

## <a name="see-also"></a>Vea también

- [Seguridad de nivel de fila](/sql/relational-databases/security/row-level-security)
- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Administrar permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Escribir SQL dinámico seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
