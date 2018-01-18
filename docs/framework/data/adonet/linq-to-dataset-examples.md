---
title: Ejemplos de LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 61e2e107c3e62569a47b4bd84e451ff55adab208
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="95399-102">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="95399-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="95399-103">Esta sección se proporciona [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ejemplos que usan los operadores de consulta estándar de programación.</span><span class="sxs-lookup"><span data-stu-id="95399-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples that use the standard query operators.</span></span> <span data-ttu-id="95399-104">El <xref:System.Data.DataSet> usa en estos ejemplos se rellena mediante la `FillDataSet` método, que se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="95399-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="95399-105">Para obtener más información, consulte [información general sobre operadores de consulta estándar](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="95399-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95399-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="95399-106">In This Section</span></span>  
 [<span data-ttu-id="95399-107">Ejemplos de expresiones de consultas</span><span class="sxs-lookup"><span data-stu-id="95399-107">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="95399-108">Contiene los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="95399-108">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="95399-109">Proyección</span><span class="sxs-lookup"><span data-stu-id="95399-109">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
-   [<span data-ttu-id="95399-110">Restricción</span><span class="sxs-lookup"><span data-stu-id="95399-110">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
-   [<span data-ttu-id="95399-111">Particionamiento</span><span class="sxs-lookup"><span data-stu-id="95399-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
  
-   [<span data-ttu-id="95399-112">Ordenación</span><span class="sxs-lookup"><span data-stu-id="95399-112">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="95399-113">Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="95399-113">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="95399-114">Operadores de agregado</span><span class="sxs-lookup"><span data-stu-id="95399-114">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="95399-115">Operadores de combinación</span><span class="sxs-lookup"><span data-stu-id="95399-115">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="95399-116">Ejemplos de consultas basadas en métodos</span><span class="sxs-lookup"><span data-stu-id="95399-116">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="95399-117">Contiene los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="95399-117">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="95399-118">Proyección</span><span class="sxs-lookup"><span data-stu-id="95399-118">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
  
-   [<span data-ttu-id="95399-119">Particionamiento</span><span class="sxs-lookup"><span data-stu-id="95399-119">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
  
-   [<span data-ttu-id="95399-120">Ordenación</span><span class="sxs-lookup"><span data-stu-id="95399-120">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="95399-121">Operadores Set</span><span class="sxs-lookup"><span data-stu-id="95399-121">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
  
-   [<span data-ttu-id="95399-122">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="95399-122">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
  
-   [<span data-ttu-id="95399-123">Operadores de elementos</span><span class="sxs-lookup"><span data-stu-id="95399-123">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="95399-124">Operadores de agregado</span><span class="sxs-lookup"><span data-stu-id="95399-124">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="95399-125">Join</span><span class="sxs-lookup"><span data-stu-id="95399-125">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="95399-126">Ejemplos de operadores específicos de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="95399-126">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="95399-127">Contiene ejemplos que demuestran cómo usar el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> y la clase <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="95399-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95399-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="95399-128">See Also</span></span>  
 [<span data-ttu-id="95399-129">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="95399-129">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [<span data-ttu-id="95399-130">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="95399-130">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
