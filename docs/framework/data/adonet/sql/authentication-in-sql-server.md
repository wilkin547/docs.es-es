---
title: Autenticación en SQL Server
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 1c918df5de4a66c00f6fd9b9dd1719ac05041ce1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="0e72e-102">Autenticación en SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e72e-102">Authentication in SQL Server</span></span>
<span data-ttu-id="0e72e-103">SQL Server admite dos modos de autenticación, el modo de autenticación de Windows y el modo mixto.</span><span class="sxs-lookup"><span data-stu-id="0e72e-103">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
-   <span data-ttu-id="0e72e-104">La autenticación de Windows es el modo predeterminado, y a menudo se denomina seguridad integrada debido a que este modelo de seguridad de SQL Server está estrechamente integrado con Windows.</span><span class="sxs-lookup"><span data-stu-id="0e72e-104">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="0e72e-105">Para iniciar sesión en SQL Server, se confía en las cuentas de usuario y grupo específicas de Windows.</span><span class="sxs-lookup"><span data-stu-id="0e72e-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="0e72e-106">Los usuarios de Windows que ya hayan sido autenticados no tienen que presentar credenciales adicionales.</span><span class="sxs-lookup"><span data-stu-id="0e72e-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
-   <span data-ttu-id="0e72e-107">El modo mixto admite la autenticación tanto de Windows como de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-107">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="0e72e-108">Los pares de nombre de usuario y contraseña se mantienen en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-108">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e72e-109">Se recomienda utilizar la autenticación de Windows siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="0e72e-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="0e72e-110">Este modo de autenticación usa una serie de mensajes cifrados para autenticar usuarios en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-110">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="0e72e-111">Cuando se usan los inicios de sesión de SQL Server, sus nombres y contraseñas se pasan a través de la red, lo que hace de éste un método menos seguro.</span><span class="sxs-lookup"><span data-stu-id="0e72e-111">When SQL Server logins are used, SQL Server login names and passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="0e72e-112">Con la autenticación de Windows, los usuarios ya registrados en Windows no tienen que iniciar sesión por separado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="0e72e-113">El siguiente valor de `SqlConnection.ConnectionString` especifica la autenticación de Windows sin que sea necesario especificar un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="0e72e-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring the a user name or password.</span></span>  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  <span data-ttu-id="0e72e-114">Los inicios de sesión son distintos de los usuarios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0e72e-114">Logins are distinct from database users.</span></span> <span data-ttu-id="0e72e-115">Los inicios de sesión o grupos de Windows se deben asignar a usuarios o roles de base de datos en una operación independiente.</span><span class="sxs-lookup"><span data-stu-id="0e72e-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="0e72e-116">A continuación se conceden permisos a los usuarios o los roles para obtener acceso a los objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0e72e-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="0e72e-117">Escenarios de autenticación</span><span class="sxs-lookup"><span data-stu-id="0e72e-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="0e72e-118">Por lo general la autenticación de Windows es la mejor opción en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="0e72e-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
-   <span data-ttu-id="0e72e-119">Existe un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="0e72e-119">There is a domain controller.</span></span>  
  
-   <span data-ttu-id="0e72e-120">La aplicación y la base de datos se encuentran en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="0e72e-120">The application and the database are on the same computer.</span></span>  
  
-   <span data-ttu-id="0e72e-121">Está usando una instancia de SQL Server Express o LocalDB.</span><span class="sxs-lookup"><span data-stu-id="0e72e-121">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="0e72e-122">Los inicios de sesión de SQL se usan habitualmente en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="0e72e-122">SQL Server logins are often used in the following situations:</span></span>  
  
-   <span data-ttu-id="0e72e-123">Si se tiene un grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e72e-123">If you have a workgroup.</span></span>  
  
-   <span data-ttu-id="0e72e-124">Los usuarios se conectan desde diferentes dominios que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="0e72e-124">Users connect from different, non-trusted domains.</span></span>  
  
-   <span data-ttu-id="0e72e-125">Aplicaciones de Internet, como [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e72e-125">Internet applications, such as [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e72e-126">La especificación de la autenticación de Windows no deshabilita los inicios de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-126">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="0e72e-127">Use el ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] instrucción para deshabilitar los inicios de sesión de SQL Server con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="0e72e-127">Use the ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="0e72e-128">Tipos de inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="0e72e-128">Login Types</span></span>  
 <span data-ttu-id="0e72e-129">SQL Server admite tres tipos de inicios de sesión:</span><span class="sxs-lookup"><span data-stu-id="0e72e-129">SQL Server supports three types of logins:</span></span>  
  
-   <span data-ttu-id="0e72e-130">Una cuenta de usuario de Windows local o una cuenta de dominio de confianza.</span><span class="sxs-lookup"><span data-stu-id="0e72e-130">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="0e72e-131">SQL Server se basa en Windows para autenticar las cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="0e72e-131">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
-   <span data-ttu-id="0e72e-132">Grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="0e72e-132">Windows group.</span></span> <span data-ttu-id="0e72e-133">Cuando se concede acceso a un grupo de Windows, se concede acceso a todos los inicios de sesión de usuario de Windows miembros de dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="0e72e-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
-   <span data-ttu-id="0e72e-134">Inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-134">SQL Server login.</span></span> <span data-ttu-id="0e72e-135">SQL Server almacena el nombre de usuario y un valor hash de la contraseña en la base de datos maestra, y usa métodos internos de autenticación para comprobar los intentos de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0e72e-135">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e72e-136">SQL Server proporciona los inicios de sesión creados con certificados o claves asimétricas que se usan únicamente para la firma de código.</span><span class="sxs-lookup"><span data-stu-id="0e72e-136">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="0e72e-137">No se pueden utilizar para conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-137">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="0e72e-138">Modo mixto de autenticación</span><span class="sxs-lookup"><span data-stu-id="0e72e-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="0e72e-139">Si tiene que usar el modo mixto de autenticación, debe crear inicios de sesión de SQL Server, que se almacenan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-139">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="0e72e-140">A continuación, debe proporcionar el nombre de usuario y la contraseña de SQL Server en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e72e-140">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e72e-141">SQL Server se instala con un inicio de sesión de SQL Server denominado `sa` (como abreviatura de "system administrator", administrador de sistema).</span><span class="sxs-lookup"><span data-stu-id="0e72e-141">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="0e72e-142">Asigne una contraseña segura al inicio de sesión `sa` y no use el inicio de sesión `sa` en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e72e-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="0e72e-143">El inicio de sesión `sa` se asigna al rol fijo de servidor `sysadmin`, que dispone de credenciales administrativas irrevocables en todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="0e72e-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="0e72e-144">Si un atacante obtiene acceso como administrador de sistema, los daños pueden ser incalculables.</span><span class="sxs-lookup"><span data-stu-id="0e72e-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="0e72e-145">Todos los miembros del grupo `BUILTIN\Administrators` de Windows (el grupo de administradores locales) son miembros del rol `sysadmin` de forma predeterminada, pero se pueden quitar de este rol.</span><span class="sxs-lookup"><span data-stu-id="0e72e-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="0e72e-146">SQL Server proporciona mecanismos de directiva de contraseñas de Windows para los inicios de sesión de SQL Server cuando se ejecuta [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0e72e-146">SQL Server provides Windows password policy mechanisms for SQL Server logins when it is running on [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] or later versions.</span></span> <span data-ttu-id="0e72e-147">Las directivas de complejidad de contraseñas están diseñadas para impedir ataques por fuerza bruta mediante el aumento del número de contraseñas posibles.</span><span class="sxs-lookup"><span data-stu-id="0e72e-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="0e72e-148">SQL Server puede aplicar las mismas directivas de complejidad y expiración en la que se usan en [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] a las contraseñas que se usan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-148">SQL Server can apply the same complexity and expiration policies used in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e72e-149">Cuando se utiliza la concatenación de cadenas de conexión a partir de la entrada de usuario, el sistema se hace vulnerable ante los ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e72e-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="0e72e-150">Utilice <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e72e-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="0e72e-151">Para obtener más información, consulte [generadores de cadenas de conexión](../../../../../docs/framework/data/adonet/connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="0e72e-151">For more information, see [Connection String Builders](../../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="0e72e-152">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="0e72e-152">External Resources</span></span>  
 <span data-ttu-id="0e72e-153">Para obtener más información, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="0e72e-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="0e72e-154">Recurso</span><span class="sxs-lookup"><span data-stu-id="0e72e-154">Resource</span></span>|<span data-ttu-id="0e72e-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e72e-155">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0e72e-156">[Las entidades de seguridad](http://msdn.microsoft.com/library/bb543165.aspx) en libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e72e-156">[Principals](http://msdn.microsoft.com/library/bb543165.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="0e72e-157">Describe los inicios de sesión y otras entidades de seguridad de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e72e-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e72e-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e72e-158">See Also</span></span>  
 [<span data-ttu-id="0e72e-159">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0e72e-159">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="0e72e-160">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e72e-160">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="0e72e-161">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="0e72e-161">Connecting to a Data Source</span></span>](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="0e72e-162">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="0e72e-162">Connection Strings</span></span>](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="0e72e-163">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0e72e-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
