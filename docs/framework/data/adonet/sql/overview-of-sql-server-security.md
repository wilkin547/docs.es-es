---
title: "Información general sobre la seguridad de SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ff0a78a852bdbf2fa1eb075273cad317c21fb182
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="overview-of-sql-server-security"></a><span data-ttu-id="24f03-102">Información general sobre la seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-102">Overview of SQL Server Security</span></span>
<span data-ttu-id="24f03-103">Una estrategia de defensa exhaustiva, con niveles superpuestos de seguridad, es la mejor manera de enfrentarse a las amenazas a la seguridad.</span><span class="sxs-lookup"><span data-stu-id="24f03-103">A defense-in-depth strategy, with overlapping layers of security, is the best way to counter security threats.</span></span> <span data-ttu-id="24f03-104">SQL Server proporciona una arquitectura de seguridad diseñada para permitir a los administradores de bases de datos y desarrolladores crear aplicaciones de base de datos seguras y contrarrestar las amenazas.</span><span class="sxs-lookup"><span data-stu-id="24f03-104">SQL Server provides a security architecture that is designed to allow database administrators and developers to create secure database applications and counter threats.</span></span> <span data-ttu-id="24f03-105">En cada versión de SQL Server se han introducido mejoras a las versiones anteriores con nuevas características y funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="24f03-105">Each version of SQL Server has improved on previous versions of SQL Server with the introduction of new features and functionality.</span></span> <span data-ttu-id="24f03-106">No obstante, la seguridad no es una característica integrada más.</span><span class="sxs-lookup"><span data-stu-id="24f03-106">However, security does not ship in the box.</span></span> <span data-ttu-id="24f03-107">Cada aplicación tiene requisitos de seguridad propios.</span><span class="sxs-lookup"><span data-stu-id="24f03-107">Each application is unique in its security requirements.</span></span> <span data-ttu-id="24f03-108">Los desarrolladores tienen que saber cuál es la combinación de características y funcionalidades más apropiada para contrarrestar las amenazas conocidas, así como anticiparse a las que puedan ir apareciendo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="24f03-108">Developers need to understand which combination of features and functionality are most appropriate to counter known threats, and to anticipate threats that may arise in the future.</span></span>  
  
 <span data-ttu-id="24f03-109">Una instancia de SQL Server contiene un conjunto jerárquico de entidades, empezando por el servidor.</span><span class="sxs-lookup"><span data-stu-id="24f03-109">A SQL Server instance contains a hierarchical collection of entities, starting with the server.</span></span> <span data-ttu-id="24f03-110">Cada servidor contiene varias bases de datos y, a su vez, cada base de datos contiene una colección de objetos susceptibles de ser protegidos.</span><span class="sxs-lookup"><span data-stu-id="24f03-110">Each server contains multiple databases, and each database contains a collection of securable objects.</span></span> <span data-ttu-id="24f03-111">Cada elemento protegible de SQL Server tiene asociados *permisos* que se pueden conceder a un *principal*, que es un grupo individual, o proceso que tienen acceso a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="24f03-111">Every SQL Server securable has associated *permissions* that can be granted to a *principal*, which is an individual, group or process granted access to SQL Server.</span></span> <span data-ttu-id="24f03-112">El marco de seguridad de SQL Server administra el acceso a entidades protegidas mediante *autenticación* y *autorización*.</span><span class="sxs-lookup"><span data-stu-id="24f03-112">The SQL Server security framework manages access to securable entities through *authentication* and *authorization*.</span></span>  
  
-   <span data-ttu-id="24f03-113">La autenticación es el proceso de inicio de sesión en SQL Server por el que una entidad de seguridad solicita el acceso mediante el envío de credenciales que el servidor evalúa.</span><span class="sxs-lookup"><span data-stu-id="24f03-113">Authentication is the process of logging on to SQL Server by which a principal requests access by submitting credentials that the server evaluates.</span></span> <span data-ttu-id="24f03-114">La autenticación establece la identidad del usuario o proceso que se autentica.</span><span class="sxs-lookup"><span data-stu-id="24f03-114">Authentication establishes the identity of the user or process being authenticated.</span></span>  
  
-   <span data-ttu-id="24f03-115">La autorización es el proceso con el que se determinan los recursos susceptibles de protegerse a los que tiene acceso una entidad de seguridad, así como las operaciones que les están permitidas a dichos recursos.</span><span class="sxs-lookup"><span data-stu-id="24f03-115">Authorization is the process of determining which securable resources a principal can access, and which operations are allowed for those resources.</span></span>  
  
 <span data-ttu-id="24f03-116">Los temas de esta sección abordan los conceptos básicos de seguridad de SQL Server y proporcionan vínculos a la documentación completa de la versión de los Libros en pantalla de SQL Server que corresponda.</span><span class="sxs-lookup"><span data-stu-id="24f03-116">The topics in this section cover SQL Server security fundamentals, providing links to the complete documentation in the relevant version of SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24f03-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="24f03-117">In This Section</span></span>  
 [<span data-ttu-id="24f03-118">Autenticación en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-118">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 <span data-ttu-id="24f03-119">Describe los inicios de sesión y autenticación en SQL Server y proporciona vínculos a recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="24f03-119">Describes logins and authentication in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="24f03-120">Roles de servidor y base de datos en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-120">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 <span data-ttu-id="24f03-121">Describe funciones fijas de bases de datos y servidores, funciones de base de datos personalizadas y cuentas integradas, y proporciona vínculos a recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="24f03-121">Describes fixed server and database roles, custom database roles, and built-in accounts and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="24f03-122">Propiedad y separación de esquemas de usuario en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-122">Ownership and User-Schema Separation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 <span data-ttu-id="24f03-123">Describe la propiedad de los objetos y separación entre usuario y esquema, y proporciona vínculos a recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="24f03-123">Describes object ownership and  user-schema separation and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="24f03-124">Autorización y permisos en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-124">Authorization and Permissions in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 <span data-ttu-id="24f03-125">Describe la concesión de permisos a través del principio de los privilegios mínimos y proporciona vínculos a recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="24f03-125">Describes granting permissions using the principle of least privilege and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="24f03-126">Cifrado de datos en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-126">Data Encryption in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 <span data-ttu-id="24f03-127">Describe las opciones de cifrado de datos en SQL Server y proporciona vínculos a recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="24f03-127">Describes data encryption options in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="24f03-128">Seguridad de integración de CLR en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-128">CLR Integration Security in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 <span data-ttu-id="24f03-129">Proporciona vínculos a recursos de seguridad de la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="24f03-129">Provides links to CLR integration security resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f03-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="24f03-130">See Also</span></span>  
 [<span data-ttu-id="24f03-131">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="24f03-131">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="24f03-132">Seguridad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-132">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [<span data-ttu-id="24f03-133">Escenarios de seguridad de aplicaciones en SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f03-133">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="24f03-134">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="24f03-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
