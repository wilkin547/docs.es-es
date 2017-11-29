---
title: Roles de servidor y base de datos en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5482dfdb-e498-4614-8652-b174829eed13
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0bcb42e018f5e62179924634bfa49fcbfc4c7d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="server-and-database-roles-in-sql-server"></a>Roles de servidor y base de datos en SQL Server
Todas las versiones de SQL Server usan la seguridad basada en roles, que permite asignar permisos a un rol, o grupo de usuarios, en lugar de asignarlos a usuarios individuales. Los roles fijos de servidor y base de datos cuentan con un conjunto fijo de permisos asignados.  
  
## <a name="fixed-server-roles"></a>Roles fijos de servidor  
 Los roles fijos de servidor cuentan con un conjunto fijo de permisos y ámbito de servidor. Están pensadas para su uso en la administración de SQL Server y los permisos asignadas a ellas no se pueden modificar. Se pueden asignar inicios de sesión a los roles fijos de servidor sin necesidad de disponer de una cuenta de usuario en una base de datos.  
  
> [!IMPORTANT]
>  El rol fijo de servidor `sysadmin` incluye a todos los demás roles y cuenta con un ámbito ilimitado. No agregue entidades de seguridad a este rol a menos que sean de total confianza. Los miembros del rol `sysadmin` disponen de permisos administrativos irrevocables en todas las bases de datos y recursos del servidor.  
  
 Sea selectivo a la hora de agregar usuarios a los roles fijos de servidor. Por ejemplo, el rol `bulkadmin` permite a los usuarios insertar el contenido de cualquier archivo local en una tabla, lo que puede poner en peligro la integridad de los datos. Para consultar la lista completa de permisos y roles fijos de servidor, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="fixed-database-roles"></a>Roles fijos de base de datos  
 Los roles fijos de base de datos incluyen un conjunto predefinido de permisos diseñados para permitir administrar grupos de permisos con facilidad. Los miembros del rol `db_owner` pueden realizar todas las actividades de configuración y mantenimiento de la base de datos.  
  
 Para obtener más información sobre los roles predefinidos en SQL Server, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Roles de nivel de servidor](http://msdn.microsoft.com/library/ms188659.aspx) y [permisos de los Roles fijos de servidor](http://msdn.microsoft.com/library/ms175892.aspx) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla|Describe los roles fijos de servidor y los permisos asociados a ellas en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].|  
|[Roles de nivel de base de datos](http://msdn.microsoft.com/library/ms189121.aspx) y [permisos de los Roles de base de datos fija](http://msdn.microsoft.com/library/ms189612.aspx) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla|Describe los roles fijos de base de datos y los permisos asociados a ellas.|  
  
## <a name="database-roles-and-users"></a>Roles y usuarios de base de datos  
 Para trabajar con objetos de base de datos, se deben asignar inicios de sesión a cuentas de usuario de base de datos. Estos usuarios de base de datos se podrán agregar entonces a roles de base de datos y heredarán los conjuntos de permisos asociados con estos roles. Se pueden conceder todos los permisos.  
  
 A la hora de diseñar la seguridad para la aplicación, también debe tener en cuenta el rol `public`, la cuenta de usuario `dbo` y la cuenta `guest`.  
  
### <a name="the-public-role"></a>Rol public  
 El rol `public` está contenido en todas las bases de datos, incluidas las bases de datos del sistema. No se puede eliminar y no se pueden agregar ni quitar usuarios de ella. Todos los usuarios y los demás roles heredan los permisos concedidos al rol `public`, ya que pertenecen de forma predeterminada al rol `public`. Por tanto, solo debe conceder al rol `public` los permisos que desee que tengan todos los usuarios.  
  
### <a name="the-dbo-user-account"></a>Cuenta de usuario dbo  
 `dbo`, o propietario de base de datos, es una cuenta de usuario con permisos implícitos para realizar todas las actividades en la base de datos. Los miembros del rol fijo del servidor `sysadmin` se asignan automáticamente a `dbo`.  
  
> [!NOTE]
>  `dbo`También es el nombre de un esquema, como se describe en [propiedad y separación usuario-esquema en SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md).  
  
 La cuenta de usuario `dbo` se confunde a menudo con el rol fijo de base de datos `db_owner`. El ámbito de `db_owner` es una base de datos y el ámbito de `sysadmin` es el servidor completo. La pertenencia al rol `db_owner` no proporciona privilegios de usuario `dbo`.  
  
### <a name="the-guest-user-account"></a>Cuenta de usuario guest  
 Después de que un usuario se haya autenticado y se le haya permitido iniciar sesión en una instancia de SQL Server, debe existir una cuenta de usuario independiente en cada base de datos a la que tenga acceso el usuario. Si se exige una cuenta de usuario en cada base de datos, se impide que los usuarios se conecten a una instancia de SQL Server y puedan tener acceso a todas las bases de datos de un servidor. La existencia de una cuenta de usuario `guest` en la base de datos evita este requisito, ya que permite que un inicio de sesión sin cuenta de usuario de base de datos tenga acceso a una base de datos.  
  
 La cuenta `guest` es una cuenta integrada en todas las versiones de SQL Server. De forma predeterminada, está deshabilitada en las bases de datos nuevas. Si está habilitada, se puede deshabilitar mediante la revocación de su permiso CONNECT, que se lleva a cabo con la ejecución de la instrucción REVOKE CONNECT FROM GUEST de Transact-SQL.  
  
> [!IMPORTANT]
>  Se debe evitar el uso de la cuenta `guest`, ya que todos los inicios de sesión que no dispongan de permisos de base de datos propios obtendrán los permisos de base de datos concedidos a esta cuenta. Si debe usar la cuenta `guest`, concédale los permisos mínimos.  
  
 Para obtener más información sobre los inicios de sesión, los usuarios y los roles de SQL Server, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Identidad y Control de acceso](http://msdn.microsoft.com/library/bb510418.aspx) en libros en pantalla de SQL Server|Contiene vínculos a temas que describen las entidades de seguridad, los roles, las credenciales, los elementos que pueden protegerse y los permisos.|  
|[Las entidades de seguridad](http://msdn.microsoft.com/library/ms181127.aspx) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla|Describe las entidades de seguridad y contiene vínculos a temas que describen los roles de servidor y de base de datos.|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Escenarios de seguridad de la aplicación en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Autenticación en SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [Propiedad y separación usuario-esquema en SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [Autorización y permisos en SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
