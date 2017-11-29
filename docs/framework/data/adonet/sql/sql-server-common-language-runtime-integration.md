---
title: "Integración con Common Language Runtime de SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3705db8b9d359ce83c6c47bef58de327745bed44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="60cc9-102">Integración con Common Language Runtime de SQL Server</span><span class="sxs-lookup"><span data-stu-id="60cc9-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="60cc9-103">SQL Server 2005 introdujo la integración del componente Common Language Runtime (CLR) de .NET Framework para Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="60cc9-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="60cc9-104">Esto significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET y Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="60cc9-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="60cc9-105">El espacio de nombres <xref:Microsoft.SqlServer.Server> contiene un conjunto de nuevas interfaces de programación de aplicaciones (API) que permiten que el código administrado interactúe con el entorno de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60cc9-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="60cc9-106">En esta sección se describen las características y comportamientos que son específicos de la integración Common Language Runtime (CLR) de SQL Server, así como las extensiones específicas en proceso de SQL Server a ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="60cc9-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="60cc9-107">El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.</span><span class="sxs-lookup"><span data-stu-id="60cc9-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="60cc9-108">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60cc9-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="60cc9-109">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="60cc9-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="60cc9-110">Conceptos de programación integración de Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="60cc9-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="60cc9-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="60cc9-111">In This Section</span></span>  
 [<span data-ttu-id="60cc9-112">Introducción a la integración de CLR de SQL Server</span><span class="sxs-lookup"><span data-stu-id="60cc9-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="60cc9-113">Proporciona una introducción a la integración CLR de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60cc9-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="60cc9-114">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="60cc9-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="60cc9-115">Funciones definidas por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="60cc9-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="60cc9-116">Describe cómo implementar y utilizar los diferentes tipos de funciones CLR: con valores de tabla, escalares y funciones de agregado definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60cc9-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="60cc9-117">Tipos definidos por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="60cc9-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="60cc9-118">Describe cómo implementar y utilizar tipos definidos por el usuario CLR.</span><span class="sxs-lookup"><span data-stu-id="60cc9-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="60cc9-119">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="60cc9-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="60cc9-120">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="60cc9-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="60cc9-121">Describe cómo implementar y utilizar procedimientos almacenados CLR.</span><span class="sxs-lookup"><span data-stu-id="60cc9-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="60cc9-122">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="60cc9-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="60cc9-123">Desencadenadores CLR</span><span class="sxs-lookup"><span data-stu-id="60cc9-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="60cc9-124">Describe cómo implementar y utilizar desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="60cc9-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="60cc9-125">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="60cc9-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="60cc9-126">La conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="60cc9-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="60cc9-127">Describe la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="60cc9-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="60cc9-128">Comportamiento específico en proceso de SQL Server de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="60cc9-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="60cc9-129">Describe las extensiones específicas en proceso de SQL Server a ADO.NET, y la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="60cc9-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="60cc9-130">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="60cc9-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60cc9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="60cc9-131">See Also</span></span>  
 [<span data-ttu-id="60cc9-132">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="60cc9-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="60cc9-133">Crear objetos de SQL Server 2005 en código administrado</span><span class="sxs-lookup"><span data-stu-id="60cc9-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="60cc9-134">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="60cc9-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
