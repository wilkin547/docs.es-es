---
title: Autenticación en SQL Server
ms.date: 03/30/2017
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 8fc6f17cd008fe24e041c52b4e5ee8fd4d261f40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="authentication-in-sql-server"></a>Autenticación en SQL Server
SQL Server admite dos modos de autenticación, el modo de autenticación de Windows y el modo mixto.  
  
-   La autenticación de Windows es el modo predeterminado, y a menudo se denomina seguridad integrada debido a que este modelo de seguridad de SQL Server está estrechamente integrado con Windows. Para iniciar sesión en SQL Server, se confía en las cuentas de usuario y grupo específicas de Windows. Los usuarios de Windows que ya hayan sido autenticados no tienen que presentar credenciales adicionales.  
  
-   El modo mixto admite la autenticación tanto de Windows como de SQL Server. Los pares de nombre de usuario y contraseña se mantienen en SQL Server.  
  
> [!IMPORTANT]
>  Se recomienda utilizar la autenticación de Windows siempre que sea posible. Este modo de autenticación usa una serie de mensajes cifrados para autenticar usuarios en SQL Server. Cuando se usan los inicios de sesión de SQL Server, sus nombres y contraseñas se pasan a través de la red, lo que hace de éste un método menos seguro.  
  
 Con la autenticación de Windows, los usuarios ya registrados en Windows no tienen que iniciar sesión por separado en SQL Server. El siguiente valor de `SqlConnection.ConnectionString` especifica la autenticación de Windows sin que sea necesario especificar un nombre de usuario ni una contraseña.  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  Los inicios de sesión son distintos de los usuarios de base de datos. Los inicios de sesión o grupos de Windows se deben asignar a usuarios o roles de base de datos en una operación independiente. A continuación se conceden permisos a los usuarios o los roles para obtener acceso a los objetos de base de datos.  
  
## <a name="authentication-scenarios"></a>Escenarios de autenticación  
 Por lo general la autenticación de Windows es la mejor opción en las siguientes situaciones:  
  
-   Existe un controlador de dominio.  
  
-   La aplicación y la base de datos se encuentran en el mismo equipo.  
  
-   Está usando una instancia de SQL Server Express o LocalDB.  
  
 Los inicios de sesión de SQL se usan habitualmente en las siguientes situaciones:  
  
-   Si se tiene un grupo de trabajo.  
  
-   Los usuarios se conectan desde diferentes dominios que no son de confianza.  
  
-   Aplicaciones de Internet, como [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  La especificación de la autenticación de Windows no deshabilita los inicios de sesión de SQL Server. Use el ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] instrucción para deshabilitar los inicios de sesión de SQL Server con privilegios elevados.  
  
## <a name="login-types"></a>Tipos de inicios de sesión  
 SQL Server admite tres tipos de inicios de sesión:  
  
-   Una cuenta de usuario de Windows local o una cuenta de dominio de confianza. SQL Server se basa en Windows para autenticar las cuentas de usuario de Windows.  
  
-   Grupo de Windows. Cuando se concede acceso a un grupo de Windows, se concede acceso a todos los inicios de sesión de usuario de Windows miembros de dicho grupo.  
  
-   Inicio de sesión de SQL Server. SQL Server almacena el nombre de usuario y un valor hash de la contraseña en la base de datos maestra, y usa métodos internos de autenticación para comprobar los intentos de inicio de sesión.  
  
> [!NOTE]
>  SQL Server proporciona los inicios de sesión creados con certificados o claves asimétricas que se usan únicamente para la firma de código. No se pueden utilizar para conectarse a SQL Server.  
  
## <a name="mixed-mode-authentication"></a>Modo mixto de autenticación  
 Si tiene que usar el modo mixto de autenticación, debe crear inicios de sesión de SQL Server, que se almacenan en SQL Server. A continuación, debe proporcionar el nombre de usuario y la contraseña de SQL Server en tiempo de ejecución.  
  
> [!IMPORTANT]
>  SQL Server se instala con un inicio de sesión de SQL Server denominado `sa` (como abreviatura de "system administrator", administrador de sistema). Asigne una contraseña segura al inicio de sesión `sa` y no use el inicio de sesión `sa` en la aplicación. El inicio de sesión `sa` se asigna al rol fijo de servidor `sysadmin`, que dispone de credenciales administrativas irrevocables en todo el servidor. Si un atacante obtiene acceso como administrador de sistema, los daños pueden ser incalculables. Todos los miembros del grupo `BUILTIN\Administrators` de Windows (el grupo de administradores locales) son miembros del rol `sysadmin` de forma predeterminada, pero se pueden quitar de este rol.  
  
 SQL Server proporciona mecanismos de directiva de contraseñas de Windows para los inicios de sesión de SQL Server cuando se ejecuta [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] o versiones posteriores. Las directivas de complejidad de contraseñas están diseñadas para impedir ataques por fuerza bruta mediante el aumento del número de contraseñas posibles. SQL Server puede aplicar las mismas directivas de complejidad y expiración en la que se usan en [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] a las contraseñas que se usan en SQL Server.  
  
> [!IMPORTANT]
>  Cuando se utiliza la concatenación de cadenas de conexión a partir de la entrada de usuario, el sistema se hace vulnerable ante los ataques de inyección de cadenas de conexión. Utilice <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución. Para obtener más información, consulte [generadores de cadenas de conexión](../../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## <a name="external-resources"></a>Recursos externos  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Las entidades de seguridad](http://msdn.microsoft.com/library/bb543165.aspx) en libros en pantalla de SQL Server|Describe los inicios de sesión y otras entidades de seguridad de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Conexión a un origen de datos](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Cadenas de conexión](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
