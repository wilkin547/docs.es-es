---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 4995512336ee9eb6e33df011757ed533db57e76e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783786"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="4a418-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4a418-102">LINQ to DataSet</span></span>
<span data-ttu-id="4a418-103">LINQ to DataSet hace que sea más fácil y rápido consultar los datos almacenados en caché <xref:System.Data.DataSet> en un objeto.</span><span class="sxs-lookup"><span data-stu-id="4a418-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="4a418-104">En concreto, LINQ to DataSet simplifica las consultas, ya que permite a los desarrolladores escribir consultas desde el propio lenguaje de programación, en lugar de usar un lenguaje de consulta independiente.</span><span class="sxs-lookup"><span data-stu-id="4a418-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="4a418-105">Esto es especialmente útil para los desarrolladores de Visual Studio, que ahora pueden aprovechar las ventajas de la comprobación de sintaxis en tiempo de compilación, los tipos estáticos y la compatibilidad con IntelliSense que proporciona Visual Studio en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="4a418-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="4a418-106">LINQ to DataSet también puede usarse para consultar los datos que se han consolidado de uno o varios orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="4a418-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="4a418-107">Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos, como consultar datos agregados localmente y almacenar en caché en el nivel medio en aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="4a418-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="4a418-108">En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.</span><span class="sxs-lookup"><span data-stu-id="4a418-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="4a418-109">La funcionalidad de LINQ to DataSet se expone principalmente a través de los métodos <xref:System.Data.DataRowExtensions> de <xref:System.Data.DataTableExtensions> extensión de las clases y.</span><span class="sxs-lookup"><span data-stu-id="4a418-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="4a418-110">LINQ to DataSet se basa en y usa la arquitectura de ADO.NET existente y no está diseñada para reemplazar ADO.NET en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a418-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="4a418-111">El código de ADO.NET existente seguirá funcionando en una aplicación LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="4a418-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="4a418-112">La relación de LINQ to DataSet con ADO.NET y el almacén de datos se muestra en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a418-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Diagrama que muestra que LINQ to DataSet se basa en el proveedor ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="4a418-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4a418-114">In This Section</span></span>  
 [<span data-ttu-id="4a418-115">Introducción</span><span class="sxs-lookup"><span data-stu-id="4a418-115">Getting Started</span></span>](getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="4a418-116">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="4a418-116">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="4a418-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="4a418-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="4a418-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a418-118">See also</span></span>

- [<span data-ttu-id="4a418-119">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4a418-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="4a418-120">Language Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a418-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="4a418-121">LINQ y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a418-121">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="4a418-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a418-122">ADO.NET</span></span>](index.md)
