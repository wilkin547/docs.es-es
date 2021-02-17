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
# <a name="authentication-in-sql-server"></a><span data-ttu-id="77d89-103">Autenticación en SQL Server</span><span class="sxs-lookup"><span data-stu-id="77d89-103">Authentication in SQL Server</span></span>

<span data-ttu-id="77d89-104">SQL Server admite dos modos de autenticación, el modo de autenticación de Windows y el modo mixto.</span><span class="sxs-lookup"><span data-stu-id="77d89-104">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="77d89-105">La autenticación de Windows es el modo predeterminado y a veces se le conoce como seguridad integrada porque este modelo de seguridad de SQL Server está estrechamente integrado en Windows.</span><span class="sxs-lookup"><span data-stu-id="77d89-105">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="77d89-106">Se confía en las cuentas de usuario y grupo específicas de Windows para iniciar sesión en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-106">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="77d89-107">Los usuarios de Windows que ya se han autenticado no tienen que presentar credenciales adicionales.</span><span class="sxs-lookup"><span data-stu-id="77d89-107">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="77d89-108">El modo mixto admite la autenticación mediante Windows y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-108">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="77d89-109">Los pares de nombre de usuario y contraseña se mantienen en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-109">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="77d89-110">Se recomienda usar la autenticación de Windows siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="77d89-110">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="77d89-111">La autenticación de Windows usa una serie de mensajes cifrados para autenticar a los usuarios en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-111">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="77d89-112">Cuando se usan inicios de sesión de SQL Server, los nombres de inicio de sesión y las contraseñas cifrados se pasan a través de la red, lo que hace de este un método menos seguro.</span><span class="sxs-lookup"><span data-stu-id="77d89-112">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="77d89-113">Con la autenticación de Windows, los usuarios ya están registrados en Windows y no es necesario que inicien sesión por separado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-113">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="77d89-114">La siguiente `SqlConnection.ConnectionString` especifica autenticación de Windows sin que los usuarios tengan que proporcionar un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="77d89-114">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="77d89-115">Los inicios de sesión son distintos de los usuarios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="77d89-115">Logins are distinct from database users.</span></span> <span data-ttu-id="77d89-116">Debe asignar inicios de sesión o grupos de Windows a usuarios o roles de base de datos en una operación independiente.</span><span class="sxs-lookup"><span data-stu-id="77d89-116">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="77d89-117">A continuación, conceda permisos a los usuarios o roles para tener acceso a los objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="77d89-117">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="77d89-118">Escenarios de autenticación</span><span class="sxs-lookup"><span data-stu-id="77d89-118">Authentication Scenarios</span></span>  

 <span data-ttu-id="77d89-119">La autenticación de Windows suele ser la mejor opción en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="77d89-119">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="77d89-120">Hay un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="77d89-120">There is a domain controller.</span></span>  
  
- <span data-ttu-id="77d89-121">La aplicación y la base de datos están en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="77d89-121">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="77d89-122">Está usando una instancia de SQL Server Express o LocalDB.</span><span class="sxs-lookup"><span data-stu-id="77d89-122">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="77d89-123">Los inicios de sesión de SQL Server se suelen usar en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="77d89-123">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="77d89-124">Si tiene un grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="77d89-124">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="77d89-125">Los usuarios se conectan desde dominios diferentes que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="77d89-125">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="77d89-126">Aplicaciones de Internet, como ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="77d89-126">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77d89-127">La especificación de autenticación de Windows no deshabilita los inicios de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-127">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="77d89-128">Para deshabilitar los inicios de sesión de SQL Server de privilegios elevados, use la instrucción ALTER LOGIN DISABLE de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="77d89-128">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="77d89-129">Tipos de inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="77d89-129">Login Types</span></span>  

 <span data-ttu-id="77d89-130">SQL Server admite tres tipos de inicios de sesión:</span><span class="sxs-lookup"><span data-stu-id="77d89-130">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="77d89-131">Una cuenta de usuario local de Windows o una cuenta de dominio de confianza.</span><span class="sxs-lookup"><span data-stu-id="77d89-131">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="77d89-132">SQL Server se basa en Windows para autenticar las cuentas de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="77d89-132">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="77d89-133">Grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="77d89-133">Windows group.</span></span> <span data-ttu-id="77d89-134">La concesión de acceso a un grupo de Windows otorga acceso a todos los inicios de sesión de usuario de Windows que son miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="77d89-134">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="77d89-135">Inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-135">SQL Server login.</span></span> <span data-ttu-id="77d89-136">SQL Server almacena el nombre de usuario y un hash de la contraseña en la base de datos master mediante métodos de autenticación internos para comprobar los intentos de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="77d89-136">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77d89-137">SQL Server proporciona inicios de sesión creados a partir de certificados o claves asimétricas que solo se usan para la firma del código.</span><span class="sxs-lookup"><span data-stu-id="77d89-137">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="77d89-138">No se pueden usar para conectarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-138">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="77d89-139">Modo mixto de autenticación</span><span class="sxs-lookup"><span data-stu-id="77d89-139">Mixed Mode Authentication</span></span>  

 <span data-ttu-id="77d89-140">Si tiene que usar la autenticación de modo mixto, debe crear inicios de sesión de SQL Server, que se almacenan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-140">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="77d89-141">Luego debe proporcionar el nombre de usuario y la contraseña de SQL Server en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77d89-141">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="77d89-142">SQL Server se instala con un inicio de sesión de SQL Server denominado `sa` (una abreviatura de "administrador del sistema").</span><span class="sxs-lookup"><span data-stu-id="77d89-142">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="77d89-143">Asigne una contraseña segura al inicio de sesión de `sa` y no use el inicio de sesión `sa` en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="77d89-143">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="77d89-144">El inicio de sesión de `sa` se asigna al rol fijo de servidor `sysadmin`, que tiene credenciales administrativas irrevocables en todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="77d89-144">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="77d89-145">No hay límites para los posibles daños si un atacante obtiene acceso como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="77d89-145">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span>
  
 <span data-ttu-id="77d89-146">SQL Server proporciona mecanismos de directiva de contraseñas de Windows para inicios de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-146">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="77d89-147">Las directivas de complejidad de contraseñas están diseñadas para impedir ataques por fuerza bruta mediante el aumento del número de contraseñas posibles.</span><span class="sxs-lookup"><span data-stu-id="77d89-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="77d89-148">SQL Server puede aplicar las mismas directivas de complejidad y expiración a las contraseñas que se usan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-148">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="77d89-149">La concatenación de cadenas de conexión a partir de datos proporcionados por el usuario puede dejarle vulnerable ante ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="77d89-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="77d89-150">Utilice <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para crear cadenas de conexión sintácticamente válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77d89-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="77d89-151">Para obtener más información, vea [Generadores de cadenas de conexión](../connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="77d89-151">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="77d89-152">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="77d89-152">External Resources</span></span>  

 <span data-ttu-id="77d89-153">Para obtener más información, vea los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="77d89-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="77d89-154">Resource</span><span class="sxs-lookup"><span data-stu-id="77d89-154">Resource</span></span>|<span data-ttu-id="77d89-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="77d89-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="77d89-156">Entidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="77d89-156">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="77d89-157">Describe los inicios de sesión y otras entidades de seguridad de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77d89-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77d89-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77d89-158">See also</span></span>

- [<span data-ttu-id="77d89-159">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="77d89-159">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="77d89-160">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="77d89-160">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="77d89-161">Conectarse a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="77d89-161">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="77d89-162">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="77d89-162">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="77d89-163">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="77d89-163">ADO.NET Overview</span></span>](../ado-net-overview.md)
