---
title: Personalizar permisos con suplantación en SQL Server
ms.date: 03/30/2017
ms.assetid: dc733d09-1d6d-4af0-9c4b-8d24504860f1
ms.openlocfilehash: b5dcef80afffa7bb3722a09020c5445dbc47f16a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782472"
---
# <a name="customizing-permissions-with-impersonation-in-sql-server"></a>Personalizar permisos con suplantación en SQL Server
Muchas aplicaciones utilizan procedimientos almacenados para obtener acceso a los datos, sirviéndose del encadenamiento de propiedad para restringir el acceso a tablas base. Se pueden conceder permisos EXECUTE en procedimientos almacenados revocando o denegando permisos en las tablas base. SQL Server no comprueba los permisos del llamador si el procedimiento almacenado y las tablas tienen el mismo propietario. No obstante, el encadenamiento de propiedad no funciona si los objetos tienen distintos propietarios o en el caso de SQL dinámico.  
  
 Puede usar la cláusula EXECUTE AS en un procedimiento almacenado cuando el autor de la llamada no dispone de permisos en los objetos de base de datos a los que se hace referencia. El resultado de la cláusula EXECUTE AS es que el contexto de ejecución cambia al del usuario proxy. Todo el código, así como todas las llamadas a los desencadenadores y procedimientos almacenados anidados, se ejecutan en el contexto de seguridad del usuario proxy. El contexto de ejecución se revierte al llamador original sólo después de la ejecución o cuando se ha emitido una instrucción REVERT.  
  
## <a name="context-switching-with-the-execute-as-statement"></a>Cambio de contexto con la instrucción EXECUTE AS  
 La instrucción Transact-SQL EXECUTE AS permite cambiar el contexto de ejecución de una instrucción mediante la suplantación de otro inicio de sesión o usuario de la base de datos. Esta técnica es útil para probar consultas y procedimientos como otro usuario.  
  
```  
EXECUTE AS LOGIN = 'loginName';  
EXECUTE AS USER = 'userName';  
```  
  
 Se deben tener permisos IMPERSONATE en el inicio de sesión o usuario al que se está suplantando. Este permiso está implícito en `sysadmin` de todas las bases de datos y en los miembros del rol `db_owner` de bases de datos de las que son propietarios.  
  
## <a name="granting-permissions-with-the-execute-as-clause"></a>Conceder permisos con la cláusula EXECUTE AS  
 Se puede utilizar la cláusula EXECUTE AS del encabezado de definición de un procedimiento almacenado, un desencadenador o una función definida por el usuario (excepto funciones alineadas con valores de tabla). Esto hace que el procedimiento se ejecute en el contexto del nombre de usuario o palabra clave especificada en la cláusula EXECUTE AS. Se puede crear un usuario proxy en la base de datos que no esté asignado a un inicio de sesión, otorgándole únicamente los permisos necesarios en los objetos a los que se obtiene acceso mediante el procedimiento. Únicamente el usuario proxy especificado en la cláusula EXECUTE AS debe tener permisos en todos los objetos a los que se tiene acceso mediante el módulo.  
  
> [!NOTE]
> Algunas acciones, como TRUNCATE TABLE, no tienen permisos que se puedan conceder. Mediante la incorporación de la instrucción dentro de un procedimiento y especificando un usuario proxy que tenga permisos ALTER TABLE, puede ampliar los permisos para truncar la tabla a llamadores que tienen sólo permisos EXECUTE en el procedimiento.  
  
 El contexto especificado en la cláusula EXECUTE AS es válido mientras dure el procedimiento, incluidos los desencadenadores y procedimientos almacenados anidados. El contexto se revierte al llamador cuando se completa la ejecución o se emite una instrucción REVERT.  
  
 Son tres los pasos que implica el uso de la cláusula EXECUTE AS en un procedimiento.  
  
1. Crear un usuario proxy en la base de datos que no esté asignado a un inicio de sesión. Este no es un requisito, pero ayuda a la hora de asignar permisos.  
  
```  
CREATE USER proxyUser WITHOUT LOGIN  
```  
  
1. Conceder al usuario proxy los permisos necesarios.  
  
2. Agregar la cláusula EXECUTE AS al procedimiento almacenado o a la función definida por el usuario.  
  
```  
CREATE PROCEDURE [procName] WITH EXECUTE AS 'proxyUser' AS ...  
```  
  
> [!NOTE]
> Las aplicaciones que requieren auditoría pueden verse interrumpidas debido a que no se ha mantenido el contexto de seguridad original del llamador. Las funciones integradas que devuelven la identidad del usuario actual, como SESSION_USER, USER, o USER_NAME, devuelven el usuario asociado a la cláusula EXECUTE AS, no el llamador original.  
  
### <a name="using-execute-as-with-revert"></a>Utilizar EXECUTE AS con REVERT  
 Se puede utilizar la instrucción Transact-SQL REVERT para revertir al contexto de ejecución original.  
  
 La cláusula opcional, with no Revert cookie = @variableName, permite volver a cambiar el contexto de ejecución al autor de la llamada @variableName si la variable contiene el valor correcto. Con ello podrá volver a cambiar el contexto de ejecución al llamador en entornos donde se utiliza la agrupación de conexiones. Dado que el valor @variableName de solo lo conoce el llamador de la instrucción EXECUTE as, el llamador puede garantizar que el usuario final no puede cambiar el contexto de ejecución que invoca la aplicación. Cuando se cierra la conexión, se devuelve al grupo. Para obtener más información sobre la agrupación de conexiones en ADO.NET, vea [SQL Server agrupación de conexiones (ADO.net)](../sql-server-connection-pooling.md).  
  
### <a name="specifying-the-execution-context"></a>Especificar el contexto de ejecución  
 Además de especificar un usuario, EXECUTE AS se puede utilizar también con cualquiera de las palabras clave siguientes.  
  
- CALLER. La ejecución como CALLER es el valor predeterminado; si no se especifica otra opción, el procedimiento se ejecuta en el contexto de seguridad del llamador.  
  
- OWNER. La ejecución como OWNER ejecuta el procedimiento en el contexto del propietario del procedimiento. Si el procedimiento se crea en un esquema cuyo propietario es `dbo` o el propietario de la base de datos, el procedimiento se ejecutará con permisos restringidos.  
  
- SELF. La ejecución como SELF se ejecuta en el contexto de seguridad del creador del procedimiento almacenado. Esto es equivalente a la ejecución como un usuario especificado, en la que el usuario especificado es la persona que crea o altera el procedimiento.  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Administración de permisos con procedimientos almacenados en SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Escritura de código SQL dinámico y seguro en SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Firma de procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md)
- [Modificación de datos con procedimientos almacenados](../modifying-data-with-stored-procedures.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
