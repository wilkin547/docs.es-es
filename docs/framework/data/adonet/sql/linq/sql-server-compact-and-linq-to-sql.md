---
title: SQL Server Compact y LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: bdd1237a8eac1c278e7704f3fbf0ae8b1deeff42
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541368"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="184a1-102">SQL Server Compact y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="184a1-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="184a1-103">SQL Server Compact es la base de datos predeterminada instalada con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="184a1-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="184a1-104">Para obtener más información, vea [uso de SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="184a1-104">For more information, see [Using SQL Server Compact (Visual Studio)](/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="184a1-105">En este tema se describen las principales diferencias en el uso, la configuración, los conjuntos de características y el ámbito de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="184a1-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="184a1-106">Características de SQL Server Compact en relación con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="184a1-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="184a1-107">De forma predeterminada, SQL Server Compact se instala para todas las ediciones de Visual Studio y, por tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="184a1-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="184a1-108">Pero la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] difiere de la de una aplicación SQL Server.</span><span class="sxs-lookup"><span data-stu-id="184a1-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="184a1-109">SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="184a1-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="184a1-110">Observe las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="184a1-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="184a1-111">SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos (extensión .sdf).</span><span class="sxs-lookup"><span data-stu-id="184a1-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="184a1-112">SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="184a1-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="184a1-113">Por lo tanto, la eficacia de la comunicación con SQL Server Compact puede ser mucho mayor que la comunicación con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="184a1-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="184a1-114">Por otro lado, SQL Server Compact necesita interoperabilidad entre el código administrado y no administrado, con el costo que ello implica.</span><span class="sxs-lookup"><span data-stu-id="184a1-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="184a1-115">El tamaño del archivo DLL de SQL Server Compact es pequeño.</span><span class="sxs-lookup"><span data-stu-id="184a1-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="184a1-116">Esta característica reduce el tamaño total de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="184a1-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="184a1-117">El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="184a1-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="184a1-118">El Object Relational Designer no admite SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="184a1-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="184a1-119">Conjunto de características</span><span class="sxs-lookup"><span data-stu-id="184a1-119">Feature Set</span></span>  
 <span data-ttu-id="184a1-120">El conjunto de características SQL Server Compact es mucho más sencillo que el conjunto de características de SQL Server de las siguientes maneras que pueden afectar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="184a1-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="184a1-121">SQL Server Compact no admite las vistas ni los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="184a1-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="184a1-122">SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.</span><span class="sxs-lookup"><span data-stu-id="184a1-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="184a1-123">SQL Server Compact admite solo un subconjunto de construcciones de SQL.</span><span class="sxs-lookup"><span data-stu-id="184a1-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="184a1-124">SQL Server Compact proporciona solo un optimizador mínimo.</span><span class="sxs-lookup"><span data-stu-id="184a1-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="184a1-125">Es posible que algunas consultas agoten el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="184a1-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="184a1-126">SQL Server Compact no admite la confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="184a1-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184a1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="184a1-127">See also</span></span>

- [<span data-ttu-id="184a1-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="184a1-128">Reference</span></span>](reference.md)
