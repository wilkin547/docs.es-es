---
description: Más información acerca de cómo habilitar el acceso entre bases de datos en SQL Server
title: Habilitar el acceso entre bases de datos en SQL Server
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 4e818b4f0294fdc7edd351a1e60203357579a320
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695871"
---
# <a name="enabling-cross-database-access-in-sql-server"></a><span data-ttu-id="40b20-103">Habilitar el acceso entre bases de datos en SQL Server</span><span class="sxs-lookup"><span data-stu-id="40b20-103">Enabling Cross-Database Access in SQL Server</span></span>

<span data-ttu-id="40b20-104">Si el procedimiento de una base de datos depende de objetos incluidos en otra base de datos, se produce el encadenamiento de propiedad entre bases de datos.</span><span class="sxs-lookup"><span data-stu-id="40b20-104">Cross-database ownership chaining occurs when a procedure in one database depends on objects in another database.</span></span> <span data-ttu-id="40b20-105">Las cadenas de propiedad entre bases de datos actúan de la misma forma que el encadenamiento de propiedad en una sola base de datos, excepto en que las cadenas de propiedad continuas requieren que todos los propietarios de objeto se asignen a la misma cuenta de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="40b20-105">A cross-database ownership chain works in the same way as ownership chaining within a single database, except that an unbroken ownership chain requires that all the object owners are mapped to the same login account.</span></span> <span data-ttu-id="40b20-106">Si el objeto de origen en la base de datos de origen y los objetos de destino en las bases de datos de destino pertenecen a la misma cuenta de inicio de sesión, SQL Server no comprueba los permisos en los objetos de destino.</span><span class="sxs-lookup"><span data-stu-id="40b20-106">If the source object in the source database and the target objects in the target databases are owned by the same login account, SQL Server does not check permissions on the target objects.</span></span>  
  
## <a name="off-by-default"></a><span data-ttu-id="40b20-107">Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="40b20-107">Off By Default</span></span>  

 <span data-ttu-id="40b20-108">El encadenamiento de propiedad entre bases de datos está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="40b20-108">Ownership chaining across databases is turned off by default.</span></span> <span data-ttu-id="40b20-109">Microsoft recomienda deshabilitar el encadenamiento de propiedad entre bases de datos, ya que da lugar a los siguientes riesgos para la seguridad:</span><span class="sxs-lookup"><span data-stu-id="40b20-109">Microsoft recommends that you disable cross-database ownership chaining because it exposes you to the following security risks:</span></span>  
  
- <span data-ttu-id="40b20-110">Los propietarios de base de datos y los miembros de las funciones de base de datos `db_ddladmin` o `db_owners` pueden crear objetos que pertenezcan a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="40b20-110">Database owners and members of the `db_ddladmin` or the `db_owners` database roles can create objects that are owned by other users.</span></span> <span data-ttu-id="40b20-111">Estos objetos pueden establecer como destino objetos de otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="40b20-111">These objects can potentially target objects in other databases.</span></span> <span data-ttu-id="40b20-112">Esto significa que, si habilita el encadenamiento de propiedad entre bases de datos, debe otorgar a estos usuarios plena confianza en los datos de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="40b20-112">This means that if you enable cross-database ownership chaining, you must fully trust these users with data in all databases.</span></span>  
  
- <span data-ttu-id="40b20-113">Los usuarios con permiso CREATE DATABASE pueden crear nuevas bases de datos y adjuntar bases de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="40b20-113">Users with CREATE DATABASE permission can create new databases and attach existing databases.</span></span> <span data-ttu-id="40b20-114">Si el encadenamiento de propiedad entre bases de datos está habilitado, estos usuarios pueden tener acceso a objetos de otras bases de datos para los que podrían no disponer de privilegios desde las bases de datos creadas o adjuntadas que crean.</span><span class="sxs-lookup"><span data-stu-id="40b20-114">If cross-database ownership chaining is enabled, these users can access objects in other databases that they might not have privileges in from the newly created or attached databases that they create.</span></span>  
  
## <a name="enabling-cross-database-ownership-chaining"></a><span data-ttu-id="40b20-115">Habilitar el encadenamiento de propiedad entre bases de datos</span><span class="sxs-lookup"><span data-stu-id="40b20-115">Enabling Cross-database Ownership Chaining</span></span>  

 <span data-ttu-id="40b20-116">El encadenamiento de propiedad entre bases de datos sólo se debe habilitar en entornos donde puede tener plena confianza en los usuarios con un alto nivel de privilegios.</span><span class="sxs-lookup"><span data-stu-id="40b20-116">Cross-database ownership chaining should only be enabled in environments where you can fully trust highly-privileged users.</span></span> <span data-ttu-id="40b20-117">Se puede establecer durante la configuración de todas las bases de datos o bien de forma selectiva para bases de datos específicas mediante los comandos `sp_configure` y `ALTER DATABASE` de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="40b20-117">It can be configured during setup for all databases, or selectively for specific databases using the Transact-SQL commands `sp_configure` and `ALTER DATABASE`.</span></span>  
  
 <span data-ttu-id="40b20-118">Para configurar de forma selectiva el encadenamiento de propiedad entre bases de datos, use `sp_configure` para desactivar el encadenamiento en el servidor.</span><span class="sxs-lookup"><span data-stu-id="40b20-118">To selectively configure cross-database ownership chaining, use `sp_configure` to turn it off for the server.</span></span> <span data-ttu-id="40b20-119">A continuación, utilice el comando ALTER DATABASE con SET DB_CHAINING ON para configurar el encadenamiento de propiedad entre bases de datos únicamente para las bases de datos que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="40b20-119">Then use the ALTER DATABASE command with SET DB_CHAINING ON to configure cross-database ownership chaining for only the databases that require it.</span></span>  
  
 <span data-ttu-id="40b20-120">En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para todas las bases de datos:</span><span class="sxs-lookup"><span data-stu-id="40b20-120">The following sample turns on cross-database ownership chaining for all databases:</span></span>  
  
```sql
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 <span data-ttu-id="40b20-121">En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para bases de datos específicas:</span><span class="sxs-lookup"><span data-stu-id="40b20-121">The following sample turns on cross-database ownership chaining for specific databases:</span></span>  
  
```sql
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a><span data-ttu-id="40b20-122">SQL dinámico</span><span class="sxs-lookup"><span data-stu-id="40b20-122">Dynamic SQL</span></span>  

 <span data-ttu-id="40b20-123">El encadenamiento de propiedad entre bases de datos no funciona en los casos en que se ejecutan instrucciones SQL creadas de forma dinámica, a menos que exista el mismo usuario en ambas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="40b20-123">Cross-database ownership chaining does not work in cases where dynamically created SQL statements are executed unless the same user exists in both databases.</span></span> <span data-ttu-id="40b20-124">Puede resolver esto en SQL Server mediante la creación de un procedimiento almacenado que acceda a los datos de otra base de datos y la firma del procedimiento con un certificado que exista en ambas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="40b20-124">You can work around this in SQL Server by creating a stored procedure that accesses data in another database and signing the procedure with a certificate that exists in both databases.</span></span> <span data-ttu-id="40b20-125">Esto proporciona a los usuarios acceso a los recursos de la base de datos utilizados por el procedimiento sin concederles permisos o acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="40b20-125">This gives users access to the database resources used by the procedure without granting them database access or permissions.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="40b20-126">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="40b20-126">External Resources</span></span>  

 <span data-ttu-id="40b20-127">Para obtener más información, vea los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="40b20-127">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="40b20-128">Resource</span><span class="sxs-lookup"><span data-stu-id="40b20-128">Resource</span></span>|<span data-ttu-id="40b20-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="40b20-129">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="40b20-130">[Extender la suplantación de base de datos](/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) mediante la [opción de encadenamiento de propiedad](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option)Execute as y Cross dB.</span><span class="sxs-lookup"><span data-stu-id="40b20-130">[Extending Database Impersonation by Using EXECUTE AS](/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) and [Cross DB Ownership Chaining Option](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option).</span></span>|<span data-ttu-id="40b20-131">En los artículos se describe cómo configurar el encadenamiento de propiedad entre bases de datos para una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40b20-131">Articles describe how to configure cross-database ownership chaining for an instance of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40b20-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="40b20-132">See also</span></span>

- [<span data-ttu-id="40b20-133">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40b20-133">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="40b20-134">Información general sobre la seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="40b20-134">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="40b20-135">Administrar permisos con procedimientos almacenados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="40b20-135">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="40b20-136">Escribir SQL dinámico seguro en SQL Server</span><span class="sxs-lookup"><span data-stu-id="40b20-136">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="40b20-137">Firmar procedimientos almacenados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="40b20-137">Signing Stored Procedures in SQL Server</span></span>](signing-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="40b20-138">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40b20-138">ADO.NET Overview</span></span>](../ado-net-overview.md)
