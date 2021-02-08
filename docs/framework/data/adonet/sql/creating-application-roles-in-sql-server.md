---
description: Más información acerca de cómo crear roles de aplicación en SQL Server
title: Crear roles de aplicación en SQL Server
ms.date: 03/30/2017
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
ms.openlocfilehash: 20047d12a004230aebca1cf9d42b3893d36f3844
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786165"
---
# <a name="creating-application-roles-in-sql-server"></a>Crear roles de aplicación en SQL Server

Los roles de aplicación proporcionan un método para asignar permisos a una aplicación sin necesidad de utilizar un rol o o un usuario de base de datos. Los usuarios se pueden conectar a la base de datos, activar el rol de aplicación y asumir los permisos concedidos a la aplicación. Los permisos concedidos al rol de aplicación se mantienen mientras dura la conexión.  
  
> [!IMPORTANT]
> Los roles de aplicación se activan cuando una aplicación cliente proporciona un nombre de rol de aplicación y una contraseña en la cadena de conexión. Presentan una vulnerabilidad de seguridad en las aplicaciones de dos niveles, ya que la contraseña se debe almacenar en el equipo cliente. En una aplicación de tres niveles, puede almacenar la contraseña de forma que los usuarios de la aplicación no tengan acceso a ella.  
  
## <a name="application-role-features"></a>Características de los roles de aplicación  

 Los roles de aplicación tienen las siguientes características:  
  
- A diferencia de los roles de base de datos, los roles de aplicación no contienen miembros.  
  
- Los roles de aplicación se activan cuando una aplicación proporciona el nombre de rol de aplicación y una contraseña en el procedimiento almacenado del sistema `sp_setapprole`.  
  
- La contraseña se debe almacenar en el equipo cliente e indicar en tiempo de ejecución; los roles de aplicación no se pueden activar desde SQL Server.  
  
- La contraseña no se cifra. La contraseña del parámetro se almacena como un hash unidireccional.  
  
- Una vez activados, los permisos adquiridos durante el rol de aplicación se mantienen mientras dura la conexión.  
  
- Los roles de aplicación heredan los permisos concedidos al rol `public`.  
  
- Si un miembro del rol fijo de servidor `sysadmin` activa un rol de aplicación, el contexto de seguridad cambia al correspondiente al rol de aplicación mientras dura la conexión.  
  
- Si crea una cuenta `guest` en una base de datos que incluye un rol de aplicación, no necesita crear una cuenta de usuario de base de datos para el rol de aplicación ni para los inicios de sesión que la invoquen. Los roles de aplicación sólo pueden obtener acceso directamente a otra base de datos si existe una cuenta `guest` en la segunda base de datos.  
  
- Las funciones integradas que devuelven nombres de inicio de sesión, como SYSTEM_USER, devuelven el nombre del inicio de sesión que invocó el rol de aplicación. Las funciones integradas que devuelven nombres de usuario de base de datos devuelven el nombre del rol de aplicación.  
  
### <a name="the-principle-of-least-privilege"></a>Principio de los privilegios mínimos  

 Los roles de aplicación sólo deben recibir los permisos necesarios si la contraseña se ve comprometida. Se deben revocar los permisos al rol `public` en las bases de datos que usen roles de aplicación. Deshabilite la cuenta `guest` en cualquier base de datos a la que no desea que tengan acceso los autores de llamadas al rol de aplicación.  
  
### <a name="application-role-enhancements"></a>Mejoras de los roles de aplicación  

 El contexto de ejecución se puede volver a cambiar al autor de llamada original tras activar un rol de aplicación, lo que evita la necesidad de deshabilitar la agrupación de conexiones. El procedimiento `sp_setapprole` incluye una nueva opción que crea una cookie, que contiene información de contexto acerca del autor de la llamada. Puede revertir la sesión mediante una llamada al procedimiento `sp_unsetapprole`, al que le pasa la cookie.  
  
## <a name="application-role-alternatives"></a>Alternativas a los roles de aplicación  

 Los roles de aplicación dependen de la seguridad de una contraseña, lo que supone una posible vulnerabilidad de seguridad. Las contraseñas se pueden exponer mediante su incrustación en código de aplicación o su almacenamiento en disco.  
  
 Puede tener en cuenta las alternativas siguientes.  
  
- Usar el cambio de contexto con la instrucción EXECUTE AS y sus cláusulas NO REVERT y WITH COOKIE. Puede crear una cuenta de usuario en una base de datos que no esté asignada a un inicio de sesión. Posteriormente asignará permisos a esta cuenta. El uso de EXECUTE AS con un usuario sin inicio de sesión resulta más seguro, ya que se basa en los permisos y no en una contraseña. Para obtener más información, consulte [Personalización de permisos con suplantación en SQL Server](customizing-permissions-with-impersonation-in-sql-server.md).  
  
- Firmar procedimientos almacenados con certificados y conceder únicamente permiso para ejecutar los procedimientos. Para obtener más información, vea [firmar procedimientos almacenados en SQL Server](signing-stored-procedures-in-sql-server.md).  
  
## <a name="external-resources"></a>Recursos externos  

 Para obtener más información, vea los recursos siguientes.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Roles de aplicación](/sql/relational-databases/security/authentication-access/application-roles)|Describe cómo crear y usar roles de aplicación en SQL Server 2008.|  
  
## <a name="see-also"></a>Vea también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Información general sobre la seguridad de SQL Server](overview-of-sql-server-security.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
