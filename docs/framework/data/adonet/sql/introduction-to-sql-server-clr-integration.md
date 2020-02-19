---
title: Introducción a la integración con CLR de SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 41dd89af4f45c673cf6b7283fc39aaf91fd9963c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452414"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="ac759-102">Introducción a la integración con CLR de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac759-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="ac759-103">Common Language Runtime (CLR) es el núcleo de Microsoft .NET Framework y proporciona el entorno de ejecución de todo el código de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac759-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="ac759-104">Se hace referencia al código que se ejecuta en CLR como código administrado.</span><span class="sxs-lookup"><span data-stu-id="ac759-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="ac759-105">CLR proporciona varias funciones y servicios necesarios para la ejecución de programas, que incluyen la compilación Just-In-Time (JIT), la asignación y administración de memoria, el forzado de la seguridad de tipos, el control de excepciones, la administración de subprocesos y la seguridad.</span><span class="sxs-lookup"><span data-stu-id="ac759-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="ac759-106">Con CLR hospedado en Microsoft SQL Server (denominado integración CLR), puede crear procedimientos almacenados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario en código administrado.</span><span class="sxs-lookup"><span data-stu-id="ac759-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="ac759-107">Dado que el código administrado se compila a código nativo antes de la ejecución, puede lograr un aumento importante del rendimiento en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="ac759-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="ac759-108">El código administrado utiliza seguridad de acceso del código (CAS), vínculos a código y dominios de aplicación para impedir que los ensamblados realicen determinadas operaciones.</span><span class="sxs-lookup"><span data-stu-id="ac759-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="ac759-109">SQL Server usa CAS para ayudar a proteger el código administrado e impedir que el sistema operativo o el servidor de bases de datos se pongan en peligro.</span><span class="sxs-lookup"><span data-stu-id="ac759-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="ac759-110">El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.</span><span class="sxs-lookup"><span data-stu-id="ac759-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="ac759-111">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac759-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="ac759-112">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ac759-112">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="ac759-113">Información general sobre integración de Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="ac759-113">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="ac759-114">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="ac759-115">La característica de integración con Common Language Runtime (CLR) está desactivada de forma predeterminada en Microsoft SQL Server y se debe habilitar para utilizar los objetos que se implementan mediante la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="ac759-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="ac759-116">Para habilitar la integración con CLR mediante Transact-SQL, utilice la opción `clr enabled` del procedimiento almacenado `sp_configure` como se muestra:</span><span class="sxs-lookup"><span data-stu-id="ac759-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="ac759-117">Puede deshabilitar la integración con CLR estableciendo la opción `clr enabled` en 0.</span><span class="sxs-lookup"><span data-stu-id="ac759-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="ac759-118">Cuando deshabilita esta característica, SQL Server deja de ejecutar todas las rutinas CLR y descarga todos los dominios de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ac759-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="ac759-119">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac759-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="ac759-120">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ac759-120">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="ac759-121">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-121">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="ac759-122">Implementar un ensamblado CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="ac759-123">Una vez que los métodos CLR se han probado y comprobado en el servidor de prueba, pueden distribuirse a los servidores de producción a través de un script de implementación.</span><span class="sxs-lookup"><span data-stu-id="ac759-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="ac759-124">que se puede generar manualmente o con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ac759-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="ac759-125">Para obtener información más detallada, consulte la versión de SQL Server documentación de la versión de SQL Server que esté usando.</span><span class="sxs-lookup"><span data-stu-id="ac759-125">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="ac759-126">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ac759-126">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="ac759-127">Implementar objetos de base de datos CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-127">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="ac759-128">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-128">CLR Integration Security</span></span>  
 <span data-ttu-id="ac759-129">El modelo de seguridad de la integración de Microsoft SQL Server con Common Language Runtime (CLR) de Microsoft .NET Framework administra y protege el acceso entre diferentes tipos de objetos CLR y objetos que no son CLR que se ejecutan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac759-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="ac759-130">Para llamar a estos objetos se puede utilizar una instrucción Transact-SQL u otro objeto CLR que se ejecute en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac759-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="ac759-131">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac759-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="ac759-132">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ac759-132">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="ac759-133">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-133">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="ac759-134">Depuración de un ensamblado CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="ac759-135">Microsoft SQL Server ofrece compatibilidad con la depuración de objetos Transact-SQL y Common Language Runtime (CLR) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac759-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="ac759-136">La depuración funciona entre lenguajes: los usuarios pueden entrar sin problemas en los objetos CLR desde Transact-SQL y viceversa.</span><span class="sxs-lookup"><span data-stu-id="ac759-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="ac759-137">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac759-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="ac759-138">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ac759-138">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="ac759-139">Depurar objetos de base de datos CLR</span><span class="sxs-lookup"><span data-stu-id="ac759-139">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="ac759-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac759-140">See also</span></span>

- [<span data-ttu-id="ac759-141">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ac759-141">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="ac759-142">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ac759-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
