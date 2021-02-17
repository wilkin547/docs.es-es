---
title: Autenticación en SQL Server
description: Obtenga información sobre la autenticación con SQL Server para ADO.NET, incluido el modo de autenticación de Windows y el modo mixto.
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: a1ecc0debd584797f72a89318aadc6ccc8a41062
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100581930"
---
# <a name="authentication-in-sql-server"></a>Autenticación en SQL Server

SQL Server admite dos modos de autenticación, el modo de autenticación de Windows y el modo mixto.  
  
- La autenticación de Windows es el modo predeterminado y a veces se le conoce como seguridad integrada porque este modelo de seguridad de SQL Server está estrechamente integrado en Windows. Se confía en las cuentas de usuario y grupo específicas de Windows para iniciar sesión en SQL Server. Los usuarios de Windows que ya se han autenticado no tienen que presentar credenciales adicionales.  
  
- El modo mixto admite la autenticación mediante Windows y SQL Server. Los pares de nombre de usuario y contraseña se mantienen en SQL Server.  
  
> [!IMPORTANT]
> Se recomienda usar la autenticación de Windows siempre que sea posible. La autenticación de Windows usa una serie de mensajes cifrados para autenticar a los usuarios en SQL Server. Cuando se usan inicios de sesión de SQL Server, los nombres de inicio de sesión y las contraseñas cifrados se pasan a través de la red, lo que hace de este un método menos seguro.  
  
 Con la autenticación de Windows, los usuarios ya están registrados en Windows y no es necesario que inicien sesión por separado en SQL Server. La siguiente `SqlConnection.ConnectionString` especifica autenticación de Windows sin que los usuarios tengan que proporcionar un nombre de usuario ni una contraseña.  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> Los inicios de sesión son distintos de los usuarios de base de datos. Debe asignar inicios de sesión o grupos de Windows a usuarios o roles de base de datos en una operación independiente. A continuación, conceda permisos a los usuarios o roles para tener acceso a los objetos de base de datos.  
  
## <a name="authentication-scenarios"></a>Escenarios de autenticación  

 La autenticación de Windows suele ser la mejor opción en las siguientes situaciones:  
  
- Hay un controlador de dominio.  
  
- La aplicación y la base de datos están en el mismo equipo.  
  
- Está usando una instancia de SQL Server Express o LocalDB.  
  
 Los inicios de sesión de SQL Server se suelen usar en las siguientes situaciones:  
  
- Si tiene un grupo de trabajo.  
  
- Los usuarios se conectan desde dominios diferentes que no son de confianza.  
  
- Aplicaciones de Internet, como ASP.NET.  
  
> [!NOTE]
> La especificación de autenticación de Windows no deshabilita los inicios de sesión de SQL Server. Para deshabilitar los inicios de sesión de SQL Server de privilegios elevados, use la instrucción ALTER LOGIN DISABLE de Transact-SQL.  
  
## <a name="login-types"></a>Tipos de inicios de sesión  

 SQL Server admite tres tipos de inicios de sesión:  
  
- Una cuenta de usuario local de Windows o una cuenta de dominio de confianza. SQL Server se basa en Windows para autenticar las cuentas de usuario de Windows.  
  
- Grupo de Windows. La concesión de acceso a un grupo de Windows otorga acceso a todos los inicios de sesión de usuario de Windows que son miembros del grupo.  
  
- Inicio de sesión de SQL Server. SQL Server almacena el nombre de usuario y un hash de la contraseña en la base de datos master mediante métodos de autenticación internos para comprobar los intentos de inicio de sesión.  
  
> [!NOTE]
> SQL Server proporciona inicios de sesión creados a partir de certificados o claves asimétricas que solo se usan para la firma del código. No se pueden usar para conectarse a SQL Server.  
  
## <a name="mixed-mode-authentication"></a>Modo mixto de autenticación  

 Si tiene que usar la autenticación de modo mixto, debe crear inicios de sesión de SQL Server, que se almacenan en SQL Server. Luego debe proporcionar el nombre de usuario y la contraseña de SQL Server en tiempo de ejecución.  
  
> [!IMPORTANT]
> SQL Server se instala con un inicio de sesión de SQL Server denominado `sa` (una abreviatura de "administrador del sistema"). Asigne una contraseña segura al inicio de sesión de `sa` y no use el inicio de sesión `sa` en la aplicación. El inicio de sesión de `sa` se asigna al rol fijo de servidor `sysadmin`, que tiene credenciales administrativas irrevocables en todo el servidor. No hay límites para los posibles daños si un atacante obtiene acceso como administrador del sistema.
  
 SQL Server proporciona mecanismos de directiva de contraseñas de Windows para inicios de sesión de SQL Server. Las directivas de complejidad de contraseñas están diseñadas para impedir ataques por fuerza bruta mediante el aumento del número de contraseñas posibles. SQL Server puede aplicar las mismas directivas de complejidad y expiración a las contraseñas que se usan en SQL Server.  
  
> [!IMPORTANT]
> La concatenación de cadenas de conexión a partir de datos proporcionados por el usuario puede dejarle vulnerable ante ataques de inyección de cadenas de conexión. Utilice <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución. Para obtener más información, vea [Generadores de cadenas de conexión](../connection-string-builders.md).  
  
## <a name="external-resources"></a>Recursos externos  

 Para obtener más información, vea los recursos siguientes.  
  
|Resource|Descripción|  
|--------------|-----------------|  
|[Entidades de seguridad](/sql/relational-databases/security/authentication-access/principals-database-engine)|Describe los inicios de sesión y otras entidades de seguridad de SQL Server.|  
  
## <a name="see-also"></a>Consulte también

- [Proteger aplicaciones de ADO.NET](../securing-ado-net-applications.md)
- [Escenarios de seguridad de aplicaciones en SQL Server](application-security-scenarios-in-sql-server.md)
- [Conectarse a un origen de datos](../connecting-to-a-data-source.md)
- [Cadenas de conexión](../connection-strings.md)
- [Información general de ADO.NET](../ado-net-overview.md)
