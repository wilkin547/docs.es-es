---
title: Introducción a la integración con CLR de SQL Server
description: La integración de CLR con SQL Server admite procedimientos almacenados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario en código administrado.
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 969afd7dea4aadf88bbb69cbe85d9cd84b233e4f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194562"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="9465e-103">Introducción a la integración con CLR de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9465e-103">Introduction to SQL Server CLR Integration</span></span>

<span data-ttu-id="9465e-104">Common Language Runtime (CLR) es el núcleo de Microsoft .NET Framework y proporciona el entorno de ejecución de todo el código de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9465e-104">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="9465e-105">Se hace referencia al código que se ejecuta en CLR como código administrado.</span><span class="sxs-lookup"><span data-stu-id="9465e-105">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="9465e-106">CLR proporciona varias funciones y servicios necesarios para la ejecución de programas, que incluyen la compilación Just-In-Time (JIT), la asignación y administración de memoria, el forzado de la seguridad de tipos, el control de excepciones, la administración de subprocesos y la seguridad.</span><span class="sxs-lookup"><span data-stu-id="9465e-106">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="9465e-107">Con CLR hospedado en Microsoft SQL Server (denominado integración CLR), puede crear procedimientos almacenados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario en código administrado.</span><span class="sxs-lookup"><span data-stu-id="9465e-107">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="9465e-108">Dado que el código administrado se compila a código nativo antes de la ejecución, puede lograr un aumento importante del rendimiento en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="9465e-108">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="9465e-109">El código administrado utiliza seguridad de acceso del código (CAS), vínculos a código y dominios de aplicación para impedir que los ensamblados realicen determinadas operaciones.</span><span class="sxs-lookup"><span data-stu-id="9465e-109">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="9465e-110">SQL Server usa CAS para ayudar a proteger el código administrado e impedir que el sistema operativo o el servidor de bases de datos se pongan en peligro.</span><span class="sxs-lookup"><span data-stu-id="9465e-110">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="9465e-111">El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.</span><span class="sxs-lookup"><span data-stu-id="9465e-111">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="9465e-112">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9465e-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9465e-113">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9465e-113">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9465e-114">Información general sobre integración CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="9465e-114">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="9465e-115">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-115">Enabling CLR Integration</span></span>  

 <span data-ttu-id="9465e-116">La característica de integración con Common Language Runtime (CLR) está desactivada de forma predeterminada en Microsoft SQL Server y se debe habilitar para utilizar los objetos que se implementan mediante la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="9465e-116">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="9465e-117">Para habilitar la integración con CLR mediante Transact-SQL, utilice la opción `clr enabled` del procedimiento almacenado `sp_configure` como se muestra:</span><span class="sxs-lookup"><span data-stu-id="9465e-117">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="9465e-118">Puede deshabilitar la integración con CLR estableciendo la opción `clr enabled` en 0.</span><span class="sxs-lookup"><span data-stu-id="9465e-118">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="9465e-119">Cuando deshabilita esta característica, SQL Server deja de ejecutar todas las rutinas CLR y descarga todos los dominios de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9465e-119">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="9465e-120">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9465e-120">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9465e-121">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9465e-121">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9465e-122">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-122">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="9465e-123">Implementar un ensamblado CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-123">Deploying a CLR Assembly</span></span>  

 <span data-ttu-id="9465e-124">Una vez que los métodos CLR se han probado y comprobado en el servidor de prueba, pueden distribuirse a los servidores de producción a través de un script de implementación.</span><span class="sxs-lookup"><span data-stu-id="9465e-124">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="9465e-125">que se puede generar manualmente o con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9465e-125">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="9465e-126">Para obtener información más detallada, consulte la versión de SQL Server documentación de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="9465e-126">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9465e-127">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9465e-127">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="9465e-128">Implementar objetos de base de datos CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-128">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="9465e-129">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-129">CLR Integration Security</span></span>  

 <span data-ttu-id="9465e-130">El modelo de seguridad de la integración de Microsoft SQL Server con Common Language Runtime (CLR) de Microsoft .NET Framework administra y protege el acceso entre diferentes tipos de objetos CLR y objetos que no son CLR que se ejecutan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9465e-130">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="9465e-131">Para llamar a estos objetos se puede utilizar una instrucción Transact-SQL u otro objeto CLR que se ejecute en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9465e-131">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="9465e-132">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9465e-132">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9465e-133">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9465e-133">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9465e-134">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-134">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="9465e-135">Depuración de un ensamblado CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-135">Debugging a CLR Assembly</span></span>  

 <span data-ttu-id="9465e-136">Microsoft SQL Server ofrece compatibilidad con la depuración de objetos Transact-SQL y Common Language Runtime (CLR) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9465e-136">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="9465e-137">La depuración funciona entre lenguajes: los usuarios pueden entrar sin problemas en los objetos CLR desde Transact-SQL y viceversa.</span><span class="sxs-lookup"><span data-stu-id="9465e-137">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="9465e-138">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9465e-138">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="9465e-139">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9465e-139">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="9465e-140">Depurar objetos de base de datos CLR</span><span class="sxs-lookup"><span data-stu-id="9465e-140">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="9465e-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9465e-141">See also</span></span>

- [<span data-ttu-id="9465e-142">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9465e-142">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="9465e-143">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9465e-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
