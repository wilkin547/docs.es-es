---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 36335f90c7850fa00a15e7112b7473637250c656
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306237"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="de3e1-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="de3e1-102">LINQ to DataSet</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="de3e1-103">facilita y acelera las consultas en datos almacenados en caché en un objeto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="de3e1-103">makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="de3e1-104">En concreto, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifica la consulta permitiendo a los desarrolladores escribir consultas desde el lenguaje de programación mismo, en lugar de mediante un lenguaje de consulta independiente.</span><span class="sxs-lookup"><span data-stu-id="de3e1-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="de3e1-105">Esto es especialmente útil para los desarrolladores de Visual Studio, que ahora pueden aprovechar las ventajas de la comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense proporcionado por Visual Studio en las consultas.</span><span class="sxs-lookup"><span data-stu-id="de3e1-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="de3e1-106">también se puede usar para consultar los datos que se han consolidado de uno o más orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="de3e1-106">can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="de3e1-107">Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos, como consultar datos agregados localmente y almacenar en caché en el nivel medio en aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="de3e1-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="de3e1-108">En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.</span><span class="sxs-lookup"><span data-stu-id="de3e1-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="de3e1-109">El [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] funcionalidad se expone principalmente a través de los métodos de extensión en el <xref:System.Data.DataRowExtensions> y <xref:System.Data.DataTableExtensions> clases.</span><span class="sxs-lookup"><span data-stu-id="de3e1-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="de3e1-110">se basa en y usa la arquitectura de ADO.NET existente y no pretende reemplazar ADO.NET en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="de3e1-110">builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="de3e1-111">El código de ADO.NET existente seguirán funcionando en un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="de3e1-111">Existing ADO.NET code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="de3e1-112">La relación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] a ADO.NET y los datos almacenados se muestran en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="de3e1-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Diagrama que muestra que LINQ to DataSet se basa en el proveedor de ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="de3e1-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="de3e1-114">In This Section</span></span>  
 [<span data-ttu-id="de3e1-115">Introducción</span><span class="sxs-lookup"><span data-stu-id="de3e1-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="de3e1-116">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="de3e1-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="de3e1-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="de3e1-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="de3e1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="de3e1-118">See also</span></span>

- [<span data-ttu-id="de3e1-119">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="de3e1-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="de3e1-120">Language Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de3e1-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="de3e1-121">LINQ y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de3e1-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="de3e1-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de3e1-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
