---
title: Habilitar el acceso entre bases de datos en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
caps.latest.revision: "10"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 720c4c8eecc20b971eb9ecf1abb85da1e72e3c54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-cross-database-access-in-sql-server"></a><span data-ttu-id="78774-102">Habilitar el acceso entre bases de datos en SQL Server</span><span class="sxs-lookup"><span data-stu-id="78774-102">Enabling Cross-Database Access in SQL Server</span></span>
<span data-ttu-id="78774-103">Si el procedimiento de una base de datos depende de objetos incluidos en otra base de datos, se produce el encadenamiento de propiedad entre bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78774-103">Cross-database ownership chaining occurs when a procedure in one database depends on objects in another database.</span></span> <span data-ttu-id="78774-104">Las cadenas de propiedad entre bases de datos actúan de la misma forma que el encadenamiento de propiedad en una sola base de datos, excepto en que las cadenas de propiedad continuas requieren que todos los propietarios de objeto se asignen a la misma cuenta de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="78774-104">A cross-database ownership chain works in the same way as ownership chaining within a single database, except that an unbroken ownership chain requires that all the object owners are mapped to the same login account.</span></span> <span data-ttu-id="78774-105">Si el objeto de origen en la base de datos de origen y los objetos de destino en las bases de datos de destino pertenecen a la misma cuenta de inicio de sesión, SQL Server no comprueba los permisos en los objetos de destino.</span><span class="sxs-lookup"><span data-stu-id="78774-105">If the source object in the source database and the target objects in the target databases are owned by the same login account, SQL Server does not check permissions on the target objects.</span></span>  
  
## <a name="off-by-default"></a><span data-ttu-id="78774-106">Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="78774-106">Off By Default</span></span>  
 <span data-ttu-id="78774-107">El encadenamiento de propiedad entre bases de datos está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="78774-107">Ownership chaining across databases is turned off by default.</span></span> <span data-ttu-id="78774-108">Microsoft recomienda deshabilitar el encadenamiento de propiedad entre bases de datos, ya que da lugar a los siguientes riesgos para la seguridad:</span><span class="sxs-lookup"><span data-stu-id="78774-108">Microsoft recommends that you disable cross-database ownership chaining because it exposes you to the following security risks:</span></span>  
  
-   <span data-ttu-id="78774-109">Los propietarios de base de datos y los miembros de las funciones de base de datos `db_ddladmin` o `db_owners` pueden crear objetos que pertenezcan a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="78774-109">Database owners and members of the `db_ddladmin` or the `db_owners` database roles can create objects that are owned by other users.</span></span> <span data-ttu-id="78774-110">Estos objetos pueden establecer como destino objetos de otras bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78774-110">These objects can potentially target objects in other databases.</span></span> <span data-ttu-id="78774-111">Esto significa que, si habilita el encadenamiento de propiedad entre bases de datos, debe otorgar a estos usuarios plena confianza en los datos de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78774-111">This means that if you enable cross-database ownership chaining, you must fully trust these users with data in all databases.</span></span>  
  
-   <span data-ttu-id="78774-112">Los usuarios con permiso CREATE DATABASE pueden crear nuevas bases de datos y adjuntar bases de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="78774-112">Users with CREATE DATABASE permission can create new databases and attach existing databases.</span></span> <span data-ttu-id="78774-113">Si el encadenamiento de propiedad entre bases de datos está habilitado, estos usuarios pueden tener acceso a objetos de otras bases de datos para los que podrían no disponer de privilegios desde las bases de datos creadas o adjuntadas que crean.</span><span class="sxs-lookup"><span data-stu-id="78774-113">If cross-database ownership chaining is enabled, these users can access objects in other databases that they might not have privileges in from the newly created or attached databases that they create.</span></span>  
  
## <a name="enabling-cross-database-ownership-chaining"></a><span data-ttu-id="78774-114">Habilitar el encadenamiento de propiedad entre bases de datos</span><span class="sxs-lookup"><span data-stu-id="78774-114">Enabling Cross-database Ownership Chaining</span></span>  
 <span data-ttu-id="78774-115">El encadenamiento de propiedad entre bases de datos sólo se debe habilitar en entornos donde puede tener plena confianza en los usuarios con un alto nivel de privilegios.</span><span class="sxs-lookup"><span data-stu-id="78774-115">Cross-database ownership chaining should only be enabled in environments where you can fully trust highly-privileged users.</span></span> <span data-ttu-id="78774-116">Se puede configurar durante la instalación para todas las bases de datos o de manera selectiva para bases de datos específicas mediante los comandos [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `sp_configure` y `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="78774-116">It can be configured during setup for all databases, or selectively for specific databases using the [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] commands `sp_configure` and `ALTER DATABASE`.</span></span>  
  
 <span data-ttu-id="78774-117">Para configurar de forma selectiva el encadenamiento de propiedad entre bases de datos, use `sp_configure` para desactivar el encadenamiento en el servidor.</span><span class="sxs-lookup"><span data-stu-id="78774-117">To selectively configure cross-database ownership chaining, use `sp_configure` to turn it off for the server.</span></span> <span data-ttu-id="78774-118">A continuación, utilice el comando ALTER DATABASE con SET DB_CHAINING ON para configurar el encadenamiento de propiedad entre bases de datos únicamente para las bases de datos que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="78774-118">Then use the ALTER DATABASE command with SET DB_CHAINING ON to configure cross-database ownership chaining for only the databases that require it.</span></span>  
  
 <span data-ttu-id="78774-119">En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para todas las bases de datos:</span><span class="sxs-lookup"><span data-stu-id="78774-119">The following sample turns on cross-database ownership chaining for all databases:</span></span>  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 <span data-ttu-id="78774-120">En el siguiente ejemplo se activa el encadenamiento de propiedad entre bases de datos para bases de datos específicas:</span><span class="sxs-lookup"><span data-stu-id="78774-120">The following sample turns on cross-database ownership chaining for specific databases:</span></span>  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a><span data-ttu-id="78774-121">SQL dinámico</span><span class="sxs-lookup"><span data-stu-id="78774-121">Dynamic SQL</span></span>  
 <span data-ttu-id="78774-122">El encadenamiento de propiedad entre bases de datos no funciona en los casos en que se ejecutan instrucciones SQL creadas de forma dinámica, a menos que exista el mismo usuario en ambas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78774-122">Cross-database ownership chaining does not work in cases where dynamically created SQL statements are executed unless the same user exists in both databases.</span></span> <span data-ttu-id="78774-123">Podrá solucionar esta situación en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] mediante la creación de procedimientos almacenados con acceso a otra base de datos y con la firma del procedimiento con un certificado que exista en ambas bases de datos.</span><span class="sxs-lookup"><span data-stu-id="78774-123">You can work around this in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] by creating a stored procedure that accesses data in another database and signing the procedure with a certificate that exists in both databases.</span></span> <span data-ttu-id="78774-124">Con ello el usuario obtiene acceso a los recursos de la base de datos que utiliza el procedimiento sin concederle permisos ni acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="78774-124">This gives users access to the database resources used by the procedure without granting them database access or permissions.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="78774-125">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="78774-125">External Resources</span></span>  
 <span data-ttu-id="78774-126">Para obtener más información, vea los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="78774-126">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="78774-127">Recurso</span><span class="sxs-lookup"><span data-stu-id="78774-127">Resource</span></span>|<span data-ttu-id="78774-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="78774-128">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="78774-129">[Extender la suplantación de la base de datos mediante EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) y [Cross DB Ownership Chaining (opción)](http://msdn.microsoft.com/library/ms188694.aspx) [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="78774-129">[Extending Database Impersonation by Using EXECUTE AS](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx) and [Cross DB Ownership Chaining Option](http://msdn.microsoft.com/library/ms188694.aspx)[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>|<span data-ttu-id="78774-130">En los temas se describe cómo configurar el encadenamiento de propiedad entre bases de datos para una instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78774-130">Topics describe how to configure cross-database ownership chaining for an instance of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78774-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="78774-131">See Also</span></span>  
 [<span data-ttu-id="78774-132">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="78774-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="78774-133">Información general de seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="78774-133">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="78774-134">Administrar permisos con procedimientos almacenados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="78774-134">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="78774-135">Escribir SQL dinámico seguro en SQL Server</span><span class="sxs-lookup"><span data-stu-id="78774-135">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="78774-136">Firmar procedimientos almacenados en SQL Server</span><span class="sxs-lookup"><span data-stu-id="78774-136">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="78774-137">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="78774-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
