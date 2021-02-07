---
description: 'Más información acerca de: SQL Server la integración con Common Language Runtime'
title: Integración con Common Language Runtime de SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 096bba0d183526ec8e5d272c5ea6a77ad0778e5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767406"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="e8bd9-103">Integración con Common Language Runtime de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8bd9-103">SQL Server Common Language Runtime Integration</span></span>

<span data-ttu-id="e8bd9-104">SQL Server 2005 introdujo la integración del componente Common Language Runtime (CLR) de .NET Framework para Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-104">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="e8bd9-105">Esto significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET y Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-105">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="e8bd9-106">El espacio de nombres <xref:Microsoft.SqlServer.Server> contiene un conjunto de nuevas interfaces de programación de aplicaciones (API) que permiten que el código administrado interactúe con el entorno de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-106">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="e8bd9-107">En esta sección se describen las características y comportamientos que son específicos de la integración Common Language Runtime (CLR) de SQL Server, así como las extensiones específicas en proceso de SQL Server a ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-107">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="e8bd9-108">El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-108">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="e8bd9-109">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-109">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e8bd9-110">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e8bd9-110">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="e8bd9-111">Conceptos de programación en el ámbito de la integración de Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="e8bd9-111">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="e8bd9-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e8bd9-112">In This Section</span></span>  

 [<span data-ttu-id="e8bd9-113">Introducción a la integración con CLR de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8bd9-113">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="e8bd9-114">Proporciona una introducción a la integración CLR de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-114">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="e8bd9-115">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-115">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e8bd9-116">Funciones CLR definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e8bd9-116">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="e8bd9-117">Describe cómo implementar y usar los distintos tipos de funciones CLR: funciones de agregado definidas por el usuario, escalares y con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-117">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="e8bd9-118">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="e8bd9-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="e8bd9-119">Describe cómo implementar y usar los tipos definidos por el usuario CLR.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-119">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="e8bd9-120">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-120">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e8bd9-121">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="e8bd9-121">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="e8bd9-122">Describe cómo implementar y usar los procedimientos almacenados CLR.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-122">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="e8bd9-123">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-123">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e8bd9-124">Desencadenadores de CLR</span><span class="sxs-lookup"><span data-stu-id="e8bd9-124">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="e8bd9-125">Describe cómo implementar y usar los desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-125">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="e8bd9-126">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-126">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="e8bd9-127">La conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="e8bd9-127">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="e8bd9-128">Describe la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-128">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="e8bd9-129">Comportamiento específico en proceso de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e8bd9-129">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="e8bd9-130">Describe las extensiones específicas en proceso de SQL Server a ADO.NET, y la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-130">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="e8bd9-131">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="e8bd9-131">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bd9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8bd9-132">See also</span></span>

- [<span data-ttu-id="e8bd9-133">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e8bd9-133">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="e8bd9-134">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e8bd9-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
