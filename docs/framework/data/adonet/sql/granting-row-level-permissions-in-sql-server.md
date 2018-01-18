---
title: Conceder permisos de nivel de fila en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c086ad08e4170d0033ae32bd730b239d5541d541
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="granting-row-level-permissions-in-sql-server"></a>Conceder permisos de nivel de fila en SQL Server
En algunos casos, existe un requisito para controlar el acceso a los datos a un nivel más detallado que el que se deriva simplemente de conceder, revocar o denegar permisos. Por ejemplo, una aplicación de bases de datos de hospital puede requerir que se restrinja el acceso a los médicos individuales solo a la información relacionada con sus pacientes. Requisitos similares se producen en muchos ámbitos, como en aplicaciones financieras, legales, gubernamentales y militares. Para ayudar a resolver estos escenarios, SQL Server 2016 ofrece una característica de [seguridad por filas](https://msdn.microsoft.com/library/dn765131.aspx) que simplifica y centraliza la lógica de acceso por filas en una directiva de seguridad. Para las versiones anteriores de SQL Server, se puede lograr una funcionalidad similar con vistas para aplicar el filtrado por filas.  
  
## <a name="implementing-row-level-filtering"></a>Implementación de filtros por filas  
 El filtrado por filas se usa para la información de almacenamiento de aplicaciones en una tabla única como en el ejemplo anterior del hospital. Para implementar el filtrado por filas, cada fila tiene una columna que define un parámetro diferenciador, como un nombre de usuario, una etiqueta u otro identificador. Para crear una vista o una directiva de seguridad en la tabla, que filtre las filas a las que puede tener acceso el usuario. Después, cree procedimientos almacenados parametrizados, que controlan los tipos de consultas que el usuario puede ejecutar.  
  
 En el siguiente ejemplo se describe cómo configurar el filtrado por filas basándose en un usuario o nombre de inicio de sesión:  
  
-   Crear la tabla agregando una columna para almacenar el nombre.  
  
-   Habilite el filtrado por filas:  
  
    -   Si usa SQL Server 2016 o posterior, o [base de datos de SQL Azure](https://docs.microsoft.com/azure/sql-database/), crear una directiva de seguridad que agrega un predicado en la tabla restringir las filas devueltas a aquellas que coinciden con cualquiera al usuario de base de datos actual (usando el CURRENT_USER) función integrada) o el nombre de inicio de sesión actual (mediante la función integrada de SUSER_SNAME ()):  
  
        ```tsql  
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
  
    -   Si usa una versión de SQL Server anterior a 2016, puede lograr una funcionalidad similar con una vista:  
  
        ```tsql  
        CREATE VIEW vw_MyTable  
        AS  
            RETURN SELECT * FROM MyTable  
            WHERE UserName = SUSER_SNAME()  
        GO  
        ```  
  
-   Cree procedimientos almacenados para seleccionar, insertar, actualizar y eliminar datos. Si el filtrado está aplicado por una directiva de seguridad, los procedimientos almacenados deben llevar a cabo estas operaciones en la tabla base directamente; de lo contrario, si el filtrado está aplicado por una vista, los procedimientos almacenados deben funcionar en su lugar con la vista. La directiva de seguridad o la vista filtrarán automáticamente las filas devueltas o modificadas por las consultas de usuario, y el procedimiento almacenado ofrecerá un mayor límite de seguridad para impedir que los usuarios con acceso directo a consultas ejecuten correctamente las consultas que pueden inferir la existencia de datos filtrados.  
  
-   Para los procedimientos almacenados que insertan datos, capture el nombre de usuario utilizando el mismo rol especificado en la vista o directiva de seguridad e inserte dicho valor en la columna UserName.  
  
-   Denegar todos los permisos en las tablas (y vistas, si es aplicable) al rol `public` . Los usuarios no podrán heredar permisos de otros roles de base de datos porque el predicado de filtro se basa en nombres de inicio de sesión o usuarios, no en roles.  
  
-   Conceder permisos EXECUTE en los procedimientos almacenados a roles de bases de datos. Los usuarios sólo pueden obtener acceso a datos a través de los procedimientos almacenados proporcionados  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea el siguiente recurso.  
  
|||  
|-|-|  
|[Implementar la seguridad de nivel de fila y de celda en bases de datos clasificadas mediante SQL Server 2005](http://go.microsoft.com/fwlink/?LinkId=98227) en el sitio de SQL Server TechCenter.|Describe cómo utilizar seguridad por filas y celdas para satisfacer los requisitos de seguridad de bases de datos clasificadas.|  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de nivel de fila](https://msdn.microsoft.com/library/dn765131.aspx)  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Información general sobre la seguridad de SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Administración de permisos con procedimientos almacenados en SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Escritura de código SQL dinámico y seguro en SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
