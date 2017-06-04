---
title: "Autenticaci&#243;n en SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 9
---
# Autenticaci&#243;n en SQL Server
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] admite dos modos de autenticación, el modo de autenticación de Windows y el modo mixto.  
  
-   La autenticación de Windows es el modo predeterminado, y a menudo se denomina seguridad integrada debido a que este modelo de seguridad de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] está integrado estrechamente en Windows.  Para iniciar sesión en SQL Server, se confía en las cuentas de usuario y grupo específicas de Windows.  Los usuarios de Windows que ya hayan sido autenticados no tienen que presentar credenciales adicionales.  
  
-   El modo mixto admite la autenticación tanto de Windows como de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Los pares de nombre de usuario y contraseña se mantienen en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]
>  Se recomienda utilizar la autenticación de Windows siempre que sea posible.  La autenticación de Windows usa una serie de mensajes cifrados para autenticar usuarios en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Cuando se usan inicios de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], los nombres y contraseñas de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] se pasan a través de la red, lo que hace de este un método menos seguro.  
  
 Con la autenticación de Windows, los usuarios ya están registrados en Windows y no es necesario que inicien sesión por separado en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  El siguiente valor de `SqlConnection.ConnectionString` especifica la autenticación de Windows sin que sea necesario especificar un nombre de usuario ni una contraseña.  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  Los inicios de sesión son distintos de los usuarios de base de datos.  Los inicios de sesión o grupos de Windows se deben asignar a usuarios o roles de base de datos en una operación independiente.  A continuación se conceden permisos a los usuarios o los roles para obtener acceso a los objetos de base de datos.  
  
## Escenarios de autenticación  
 Por lo general la autenticación de Windows es la mejor opción en las siguientes situaciones:  
  
-   Existe un controlador de dominio.  
  
-   La aplicación y la base de datos se encuentran en el mismo equipo.  
  
-   Está usando una instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express o LocalDB.  
  
 Los inicios de sesión de SQL se usan habitualmente en las siguientes situaciones:  
  
-   Si se tiene un grupo de trabajo.  
  
-   Los usuarios se conectan desde diferentes dominios que no son de confianza.  
  
-   Aplicaciones de Internet, como [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
  
> [!NOTE]
>  La especificación de la autenticación de Windows no deshabilita los inicios de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Para deshabilitar los inicios de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] de privilegios elevados, use la instrucción ALTER LOGIN DISABLE de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].  
  
## Tipos de inicios de sesión  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] admite tres tipos de inicios de sesión:  
  
-   Una cuenta de usuario de Windows local o una cuenta de dominio de confianza.  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] se basa en Windows para autenticar las cuentas de usuario de Windows.  
  
-   Grupo de Windows.  Cuando se concede acceso a un grupo de Windows, se concede acceso a todos los inicios de sesión de usuario de Windows miembros de dicho grupo.  
  
-   Inicio de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] almacena el nombre de usuario y un valor hash de la contraseña en la base de datos maestra, mediante métodos de autenticación internos para comprobar los intentos de inicio de sesión.  
  
> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] proporciona inicios de sesión creados a partir de certificados o claves asimétricas que solo se usan para la firma del código.  No se pueden usar para conectarse a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## Modo mixto de autenticación  
 Si tiene que usar el modo mixto de autenticación, debe crear inicios de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], que se almacenan en SQL Server.  A continuación, debe proporcionar el nombre de usuario y la contraseña de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] en tiempo de ejecución.  
  
> [!IMPORTANT]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] se instala con un inicio de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] denominado `sa` como abreviatura en inglés de "system administrator" \(administrador de sistema\).  Asigne una contraseña segura al inicio de sesión `sa` y no use el inicio de sesión `sa` en la aplicación.  El inicio de sesión `sa` se asigna al rol fijo de servidor `sysadmin`, que dispone de credenciales administrativas irrevocables en todo el servidor.  Si un atacante obtiene acceso como administrador de sistema, los daños pueden ser incalculables.  Todos los miembros del grupo `BUILTIN\Administrators` de Windows \(el grupo de administradores locales\) son miembros del rol `sysadmin` de forma predeterminada, pero se pueden quitar de este rol.  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] proporciona mecanismos de directiva de contraseñas de Windows para los inicios de sesión de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] cuando se ejecuta en [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] o versiones posteriores.  Las directivas de complejidad de contraseñas están diseñadas para impedir ataques por fuerza bruta mediante el aumento del número de contraseñas posibles.  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] puede aplicar las mismas directivas de complejidad y expiración que se usan en [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] para las contraseñas que se usan en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]
>  Cuando se utiliza la concatenación de cadenas de conexión a partir de la entrada de usuario, el sistema se hace vulnerable ante los ataques de inyección de cadenas de conexión.  Utilice <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución.  Para obtener más información, consulta [Compiladores de cadenas de conexión](../../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## Recursos externos  
 Para obtener más información, vea los siguientes recursos.  
  
|Recurso|Descripción|  
|-------------|-----------------|  
|[Entidades de seguridad \(motor de base de datos\)](http://msdn.microsoft.com/library/bb543165.aspx) en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] los Libros en pantalla.|Describe los inicios de sesión y otras entidades de seguridad de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].|  
  
## Vea también  
 [Proteger aplicaciones de ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Escenarios de seguridad de aplicaciones en SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)   
 [Conectarse a un origen de datos](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Cadenas de conexión](../../../../../docs/framework/data/adonet/connection-strings.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)