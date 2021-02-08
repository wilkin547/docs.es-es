---
description: 'Más información acerca de: SQL Server Compact y LINQ to SQL'
title: SQL Server Compact y LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: ae7965db1685d7682b643662df8fb1c1376a7154
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803716"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="0de44-103">SQL Server Compact y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0de44-103">SQL Server Compact and LINQ to SQL</span></span>

<span data-ttu-id="0de44-104">SQL Server Compact es la base de datos predeterminada instalada con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0de44-104">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="0de44-105">Para obtener más información, vea [uso de SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="0de44-105">For more information, see [Using SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="0de44-106">En este tema se describen las principales diferencias en el uso, la configuración, los conjuntos de características y el ámbito de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="0de44-106">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="0de44-107">Características de SQL Server Compact en relación con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0de44-107">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  

 <span data-ttu-id="0de44-108">De forma predeterminada, SQL Server Compact se instala para todas las ediciones de Visual Studio y, por tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0de44-108">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="0de44-109">Pero la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] difiere de la de una aplicación SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0de44-109">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="0de44-110">SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0de44-110">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="0de44-111">Observe las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="0de44-111">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="0de44-112">SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos (extensión .sdf).</span><span class="sxs-lookup"><span data-stu-id="0de44-112">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="0de44-113">SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="0de44-113">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="0de44-114">Por lo tanto, la eficacia de la comunicación con SQL Server Compact puede ser mucho mayor que la comunicación con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0de44-114">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="0de44-115">Por otro lado, SQL Server Compact necesita interoperabilidad entre el código administrado y no administrado, con el costo que ello implica.</span><span class="sxs-lookup"><span data-stu-id="0de44-115">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="0de44-116">El tamaño del archivo DLL de SQL Server Compact es pequeño.</span><span class="sxs-lookup"><span data-stu-id="0de44-116">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="0de44-117">Esta característica reduce el tamaño total de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0de44-117">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="0de44-118">El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="0de44-118">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="0de44-119">El Object Relational Designer no admite SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="0de44-119">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="0de44-120">Conjunto de características</span><span class="sxs-lookup"><span data-stu-id="0de44-120">Feature Set</span></span>  

 <span data-ttu-id="0de44-121">El conjunto de características SQL Server Compact es mucho más sencillo que el conjunto de características de SQL Server de las siguientes maneras que pueden afectar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="0de44-121">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="0de44-122">SQL Server Compact no admite las vistas ni los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="0de44-122">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="0de44-123">SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.</span><span class="sxs-lookup"><span data-stu-id="0de44-123">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="0de44-124">SQL Server Compact admite solo un subconjunto de construcciones de SQL.</span><span class="sxs-lookup"><span data-stu-id="0de44-124">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="0de44-125">SQL Server Compact proporciona solo un optimizador mínimo.</span><span class="sxs-lookup"><span data-stu-id="0de44-125">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="0de44-126">Es posible que algunas consultas agoten el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0de44-126">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="0de44-127">SQL Server Compact no admite la confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="0de44-127">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de44-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0de44-128">See also</span></span>

- [<span data-ttu-id="0de44-129">Referencia</span><span class="sxs-lookup"><span data-stu-id="0de44-129">Reference</span></span>](reference.md)
