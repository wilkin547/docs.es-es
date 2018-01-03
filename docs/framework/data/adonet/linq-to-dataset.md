---
title: LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 75ab1e733915349c64742e1a9c1142cad988ade0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-dataset"></a><span data-ttu-id="98d3f-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="98d3f-102">LINQ to DataSet</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="98d3f-103"> facilita y acelera las consultas en datos almacenados en caché en un objeto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="98d3f-103"> makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="98d3f-104">En concreto, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifica la consulta permitiendo a los desarrolladores escribir consultas en el lenguaje de programación mismo, en lugar de mediante un lenguaje de consulta independiente.</span><span class="sxs-lookup"><span data-stu-id="98d3f-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="98d3f-105">Esto es especialmente útil para [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] los desarrolladores, que ahora pueden aprovechar las ventajas de la comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense que proporciona el [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] en las consultas.</span><span class="sxs-lookup"><span data-stu-id="98d3f-105">This is especially useful for [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] in their queries.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="98d3f-106"> también se puede usar para consultar los datos que se han consolidado de uno o más orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="98d3f-106"> can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="98d3f-107">Esto permite muchos casos que requieren flexibilidad en la forma de representar y controlar los datos, como consultar datos agregados localmente y almacenar en caché en el nivel medio en aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="98d3f-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="98d3f-108">En concreto, las aplicaciones de inteligencia empresaria, análisis e informes genéricos requieren este método de manipulación.</span><span class="sxs-lookup"><span data-stu-id="98d3f-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="98d3f-109">El [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] funcionalidad se expone principalmente mediante métodos de extensión en la <xref:System.Data.DataRowExtensions> y <xref:System.Data.DataTableExtensions> clases.</span><span class="sxs-lookup"><span data-stu-id="98d3f-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="98d3f-110">se basa en y usa existente [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] arquitectura y no está destinada a reemplazar [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] en código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="98d3f-110"> builds on and uses the existing [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architecture, and is not meant to replace [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] in application code.</span></span> <span data-ttu-id="98d3f-111">El código de ADO.NET 2.0 existente continuará funcionando en una aplicación [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98d3f-111">Existing ADO.NET 2.0 code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="98d3f-112">La relación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] con [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] y los datos almacenados se muestran en el diagrama siguiente.</span><span class="sxs-lookup"><span data-stu-id="98d3f-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] and the data store is illustrated in the following diagram.</span></span>  
  
 <span data-ttu-id="98d3f-113">![LINQ to DataSet se basa en el proveedor de ADO.NET](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span><span class="sxs-lookup"><span data-stu-id="98d3f-113">![LINQ to DataSet is based on the ADO.NET Provider](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98d3f-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="98d3f-114">In This Section</span></span>  
 [<span data-ttu-id="98d3f-115">Introducción</span><span class="sxs-lookup"><span data-stu-id="98d3f-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="98d3f-116">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="98d3f-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="98d3f-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="98d3f-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="98d3f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="98d3f-118">See Also</span></span>  
 [<span data-ttu-id="98d3f-119">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="98d3f-119">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="98d3f-120">LINQ y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98d3f-120">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [<span data-ttu-id="98d3f-121">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98d3f-121">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
