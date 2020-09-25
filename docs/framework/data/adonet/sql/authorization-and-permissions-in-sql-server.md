---
title: Autorización y permisos en SQL Server
description: Obtenga información acerca de cómo conceder permisos explícitamente para hacer que los objetos de base de datos que cree sean accesibles para los usuarios de SQL Server con ADO.NET.
ms.date: 03/30/2017
ms.assetid: d340405c-91f4-4837-a3cc-a238ee89888a
ms.openlocfilehash: 748d40ff2c64ae59f43e6296ef591efcb5ff9831
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197500"
---
# <a name="authorization-and-permissions-in-sql-server"></a>Autorización y permisos en SQL Server

Al crear objetos de base de datos, se deben conceder permisos de forma explícita para que los usuarios tengan acceso a ellos. Cada objeto susceptible de protegerse tiene permisos que se pueden otorgar a una entidad de seguridad mediante instrucciones de permiso.  
  
## <a name="the-principle-of-least-privilege"></a>Principio de los privilegios mínimos  

 Desarrollar una aplicación utilizando un enfoque basado en cuenta de usuario de privilegios mínimos (LUA) constituye una parte importante de una estrategia de defensa exhaustiva contra las amenazas a la seguridad. El enfoque LUA garantiza que los usuarios siguen el principio de los privilegios mínimos y siempre inician sesión con cuentas de usuario limitadas. Las tareas administrativas se realizan utilizando roles fijos del servidor y el uso del rol fijo del servidor `sysadmin` es muy restringido.  
  
 Cuando conceda permisos a usuarios de base de datos, siga siempre el principio de los privilegios mínimos. Otorgue a usuarios y roles los mínimos permisos necesarios para que puedan realizar una tarea concreta.  
  
> [!IMPORTANT]
> Cuado se desarrolla o prueba una aplicación utilizando el enfoque LUA, se aumenta el grado de dificultad del proceso de desarrollo. Resulta más fácil crear objetos y escribir código cuando se inicia sesión como administrador del sistema o propietario de la base de datos que cuando se utiliza una cuenta LUA. Sin embargo, el desarrollo de aplicaciones con cuentas de privilegios elevados puede ofuscar el impacto de funcionalidades reducidas cuando usuarios con privilegios de nivel bajo intentan ejecutar una aplicación que requiere permisos elevados para funcionar correctamente. Otorgar a los usuarios permisos excesivos para recuperar funcionalidades perdidas puede exponer a la aplicación a posibles ataques. El diseño, desarrollo y prueba de una aplicación en la que se ha iniciado sesión con una cuenta LUA impone un enfoque disciplinado del planeamiento de la seguridad que evita sorpresas desagradables, así como la tentación de recurrir a la solución rápida de otorgar privilegios elevados. Puede utilizar un inicio de sesión de SQL Server para realizar pruebas, incluso aunque la aplicación esté pensada para implementarse con autenticación de Windows.  
  
## <a name="role-based-permissions"></a>Permisos basados en roles  

 Otorgar permisos a roles en lugar de a usuarios simplifica la administración de la seguridad. Los conjuntos de permisos asignados a roles los heredan todos los miembros del rol. Es más fácil agregar o quitar usuarios de un rol que volver a crear conjuntos de permisos distintos para cada usuario. Las roles se pueden anidar. Sin embargo, la existencia de demasiados niveles de anidamiento puede reducir el rendimiento. También puede agregar usuarios a roles fijos de bases de datos para simplificar los permisos de asignación.  
  
 Puede conceder permisos en el nivel de esquema. Los usuarios heredan automáticamente los permisos en todos los objetos nuevos creados en el esquema; no es necesario otorgar permisos cuando se crean objetos nuevos.  
  
## <a name="permissions-through-procedural-code"></a>Permisos a mediante código basado en procedimiento  

 El encapsulamiento del acceso a los datos a través de módulos tales como procedimientos almacenados y funciones definidas por el usuario brinda un nivel de protección adicional a la aplicación. Se puede evitar que los usuarios interactúen directamente con objetos de la base de datos otorgando permisos solo a procedimientos almacenados o funciones, y denegando permisos a objetos subyacentes tales como tablas. SQL Server lo consigue mediante encadenamiento de propiedad.  
  
## <a name="permission-statements"></a>Instrucciones de permiso  

 En la siguiente tabla se describen las tres instrucciones de permiso de Transact-SQL.  
  
|Instrucción de permiso|Descripción|  
|--------------------------|-----------------|  
|GRANT|Concede un permiso.|  
|REVOKE|Revoca un permiso. Este es el estado predeterminado de un objeto nuevo. Un permiso revocado a un usuario o rol se puede heredar de otros grupos o roles a los que está asignada la entidad de seguridad.|  
|DENEGAR|DENY revoca un permiso de manera que no pueda ser heredado. DENY tiene prioridad sobre todos los permisos, pero no se aplica a propietarios de objeto o miembros de `sysadmin`. Si deniega permisos a un objeto en el rol `public`, se los deniega igualmente a todos los usuarios y roles excepto a los propietarios del objeto y a los miembros de `sysadmin`.|  
  
- La instrucción GRANT puede asignar permisos a un grupo o rol que puede ser heredada por los usuarios de la base de datos. No obstante, la instrucción DENY tiene prioridad sobre el resto de las instrucciones de permiso. Por ello, un usuario al que se le ha denegado un permiso no puede heredarlo de otro rol.  
  
> [!NOTE]
> A los miembros del rol fijo del servidor `sysadmin` y a los propietarios de objetos no se les pueden denegar permisos.  
  
## <a name="ownership-chains"></a>Cadenas de propiedad  

 SQL Server garantiza que solamente puedan tener acceso a los objetos las entidades de seguridad a las que se les han concedido permisos. Cuando varios objetos de base de datos tienen acceso el uno al otro, la secuencia se conoce como "cadena". Cuando SQL Server atraviesa los vínculos de la cadena, evalúa los permisos de manera diferente a como lo haría si estuviera obteniendo acceso a cada elemento separadamente. Cuando se obtiene acceso a un objeto a través de una cadena, SQL Server primero compara al propietario del objeto con el propietario del objeto de llamada (el vínculo anterior de la cadena). Si ambos objetos tienen el mismo propietario, los permisos del objeto al que se hace referencia no se comprueban. Siempre que un objeto obtiene acceso a otro objeto que tiene un propietario distinto, la cadena de propiedad se rompe y SQL Server debe comprobar el contexto de seguridad del llamador.  
  
## <a name="procedural-code-and-ownership-chaining"></a>Código basado en procedimiento y encadenamiento de propiedad  

 Suponga que a un usuario se le otorgan permisos para ejecutar en un procedimiento almacenado que selecciona datos desde una tabla. Si el procedimiento almacenado y la tabla tienen el mismo propietario, el usuario no necesita ningún permiso en la tabla y se le pueden incluso denegar permisos. Sin embargo, si el procedimiento almacenado y la tabla tienen distintos propietarios, SQL Server debe comprobar los permisos del usuario en la tabla antes de permitirle el acceso a los datos.  
  
> [!NOTE]
> El encadenamiento de propiedad no se aplica en el caso de las instrucciones de SQL dinámico. Para llamar a un procedimiento que ejecuta una instrucción SQL, el llamador debe tener permiso de acceso a las tablas subyacentes, lo que deja a su aplicación expuesta a posibles ataques de inyección SQL. SQL Server proporciona nuevos mecanismos, como suplantación y módulos de firma con certificados, que no requieren otorgar permisos en las tablas subyacentes. Estos mecanismos se pueden utilizar también con procedimientos almacenados CLR.  
  
## <a name="external-resources"></a>Recursos externos  

 Para obtener más información, vea los recursos siguientes.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Permisos](/sql/relational-databases/security/permissions-database-engine)|Contiene temas que describen la jerarquía de permisos, las vistas de catálogo y permisos de servidores fijos y roles de bases de datos.|
  
## <a name="see-also"></a>Consulte también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Autenticación en SQL Server](authentication-in-sql-server.md)
- [Roles de servidor y base de datos en SQL Server](server-and-database-roles-in-sql-server.md)
- [Propiedad y separación de esquemas de usuario en SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
