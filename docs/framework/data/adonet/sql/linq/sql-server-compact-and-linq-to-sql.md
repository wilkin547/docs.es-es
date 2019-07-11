---
title: SQL Server Compact y LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 5fa8f8ba2b0c5bdb92ad507bd48839a26837ba41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742868"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="7a6d9-102">SQL Server Compact y LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7a6d9-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="7a6d9-103">SQL Server Compact es la base de datos predeterminada instalada con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="7a6d9-104">Para obtener más información, consulte [utilizando SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="7a6d9-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="7a6d9-105">Este tema describen las diferencias clave en uso, configuración, conjuntos de características y ámbito de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="7a6d9-106">Características de SQL Server Compact en relación con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7a6d9-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="7a6d9-107">De forma predeterminada, SQL Server Compact se instala para todas las ediciones de Visual Studio y, por tanto, está disponible en el equipo de desarrollo para su uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a6d9-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="7a6d9-108">Pero la implementación de una aplicación que usa SQL Server Compact y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] difiere de una aplicación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="7a6d9-109">SQL Server Compact no forma parte de .NET Framework y, por lo tanto, se debe incluir con la aplicación o descargar específicamente desde el sitio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="7a6d9-110">Observe las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="7a6d9-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="7a6d9-111">SQL Server Compact se empaqueta como una DLL que se puede usar directamente en archivos de base de datos (extensión .sdf).</span><span class="sxs-lookup"><span data-stu-id="7a6d9-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="7a6d9-112">SQL Server Compact se ejecuta en el mismo proceso que la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="7a6d9-113">La eficacia de la comunicación con SQL Server Compact, por tanto, puede ser significativamente mayor que con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="7a6d9-114">Por otro lado, SQL Server Compact necesita interoperabilidad entre código administrado y con su costo que ello implica.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="7a6d9-115">El tamaño de la DLL de SQL Server Compact es pequeño.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="7a6d9-116">Esta característica reduce el tamaño total de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="7a6d9-117">El tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y la herramienta de línea de comandos SQLMetal admiten SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="7a6d9-118">Object Relational Designer no admite SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="7a6d9-119">Conjunto de características</span><span class="sxs-lookup"><span data-stu-id="7a6d9-119">Feature Set</span></span>  
 <span data-ttu-id="7a6d9-120">El conjunto de características de SQL Server Compact es mucho más sencillo que el conjunto de características de SQL Server de las maneras siguientes que pueden afectar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="7a6d9-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="7a6d9-121">SQL Server Compact no admite las vistas ni los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="7a6d9-122">SQL Server Compact admite solo un subconjunto de tipos de datos y funciones de SQL.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="7a6d9-123">SQL Server Compact admite solo un subconjunto de construcciones de SQL.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="7a6d9-124">SQL Server Compact proporciona solo un optimizador mínimo.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="7a6d9-125">Es posible que algunas consultas, es posible que el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="7a6d9-126">SQL Server Compact no admite la confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="7a6d9-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a6d9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a6d9-127">See also</span></span>

- [<span data-ttu-id="7a6d9-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="7a6d9-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
