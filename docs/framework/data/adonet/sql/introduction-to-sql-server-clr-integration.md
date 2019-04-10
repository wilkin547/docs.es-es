---
title: Introducción a la integración con CLR de SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: dc7d19bf361ed5fcda1fd5edf64eeb5e4ce15a71
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336816"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="eee29-102">Introducción a la integración con CLR de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee29-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="eee29-103">Common Language Runtime (CLR) es el núcleo de Microsoft .NET Framework y proporciona el entorno de ejecución de todo el código de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eee29-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="eee29-104">El código que se ejecuta en CLR se conoce como código administrado.</span><span class="sxs-lookup"><span data-stu-id="eee29-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="eee29-105">El CLR proporciona diversas funciones y servicios necesarios para la ejecución de los programas, como compilación just-in-time (JIT), asignación y administración de memoria, aplicación de la seguridad de tipos, control de excepciones, administración de subprocesos y seguridad.</span><span class="sxs-lookup"><span data-stu-id="eee29-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="eee29-106">Con el CLR hospedado en Microsoft SQL Server (lo que se denomina integración con CLR), puede crear procedimientos almacenados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario en código administrado.</span><span class="sxs-lookup"><span data-stu-id="eee29-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="eee29-107">Como el código administrado se compila a código nativo antes de su ejecución, en algunas situaciones puede conseguir aumentos significativos del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="eee29-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="eee29-108">El código administrado utiliza seguridad de acceso del código (CAS), vínculos a código y dominios de aplicación para impedir que los ensamblados realicen determinadas operaciones.</span><span class="sxs-lookup"><span data-stu-id="eee29-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="eee29-109">SQL Server usa CAS para ayudar a proteger el código administrado e impedir que el sistema operativo o el servidor de bases de datos se pongan en peligro.</span><span class="sxs-lookup"><span data-stu-id="eee29-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="eee29-110">El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.</span><span class="sxs-lookup"><span data-stu-id="eee29-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="eee29-111">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee29-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="eee29-112">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee29-112">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="eee29-113">Información general sobre integración CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="eee29-113">Common Language Runtime (CLR) Integration Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="eee29-114">Habilitación de la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="eee29-115">La característica de integración con Common Language Runtime (CLR) está desactivada de forma predeterminada en Microsoft SQL Server y se debe habilitar para utilizar los objetos que se implementan mediante la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="eee29-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="eee29-116">Para habilitar la integración con CLR mediante Transact-SQL, utilice la opción `clr enabled` del procedimiento almacenado `sp_configure` como se muestra:</span><span class="sxs-lookup"><span data-stu-id="eee29-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="eee29-117">Puede deshabilitar la integración con CLR estableciendo la opción `clr enabled` en 0.</span><span class="sxs-lookup"><span data-stu-id="eee29-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="eee29-118">Cuando deshabilita esta característica, SQL Server deja de ejecutar todas las rutinas CLR y descarga todos los dominios de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eee29-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="eee29-119">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee29-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="eee29-120">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee29-120">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="eee29-121">Habilitación de la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-121">Enabling CLR Integration</span></span>](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="eee29-122">Implementar un ensamblado CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="eee29-123">Una vez probados y comprobados los métodos CLR en el servidor de prueba, se pueden distribuir a los servidores de producción mediante un script de implementación,</span><span class="sxs-lookup"><span data-stu-id="eee29-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="eee29-124">que se puede generar manualmente o con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="eee29-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="eee29-125">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee29-125">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="eee29-126">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee29-126">SQL Server Books Online</span></span>**  
  
1. [<span data-ttu-id="eee29-127">Implementar objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-127">Deploying CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="eee29-128">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-128">CLR Integration Security</span></span>  
 <span data-ttu-id="eee29-129">El modelo de seguridad de la integración de Microsoft SQL Server con Common Language Runtime (CLR) de Microsoft .NET Framework administra y protege el acceso entre diferentes tipos de objetos CLR y objetos que no son CLR que se ejecutan en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee29-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="eee29-130">Para llamar a estos objetos se puede utilizar una instrucción Transact-SQL u otro objeto CLR que se ejecute en el servidor.</span><span class="sxs-lookup"><span data-stu-id="eee29-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="eee29-131">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee29-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="eee29-132">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee29-132">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="eee29-133">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-133">CLR Integration Security</span></span>](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="eee29-134">Depuración de un ensamblado CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="eee29-135">Microsoft SQL Server ofrece compatibilidad con la depuración de objetos Transact-SQL y Common Language Runtime (CLR) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="eee29-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="eee29-136">La depuración funciona entre lenguajes: los usuarios pueden entrar sin problemas en los objetos CLR desde Transact-SQL y viceversa.</span><span class="sxs-lookup"><span data-stu-id="eee29-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="eee29-137">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eee29-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="eee29-138">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eee29-138">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="eee29-139">Depurar objetos de bases de datos CLR</span><span class="sxs-lookup"><span data-stu-id="eee29-139">Debugging CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a><span data-ttu-id="eee29-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="eee29-140">See also</span></span>

- [<span data-ttu-id="eee29-141">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eee29-141">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)
- [<span data-ttu-id="eee29-142">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="eee29-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
