---
title: Conceptos sobre consultas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a125749-ccb5-49d5-999d-d2db7171d74d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 907761184256b7cf51c7c0f20fa43ee603e0ab12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="query-concepts"></a><span data-ttu-id="20caf-102">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="20caf-102">Query Concepts</span></span>
<span data-ttu-id="20caf-103">En esta sección se describen los conceptos fundamentales del diseño de consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20caf-103">This section describes key concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20caf-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20caf-104">In This Section</span></span>  
 [<span data-ttu-id="20caf-105">Consultas de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="20caf-105">LINQ to SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-queries.md)  
 <span data-ttu-id="20caf-106">Hace referencia a temas generales sobre [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] y explica elementos específicos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20caf-106">Refers to general [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] topics, and explains items specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="20caf-107">Realización de consultas en varias relaciones</span><span class="sxs-lookup"><span data-stu-id="20caf-107">Querying Across Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)  
 <span data-ttu-id="20caf-108">Explica cómo utilizar las asociaciones en el modelo de objetos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20caf-108">Explains how to use associations in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="20caf-109">Ejecución remota o ejecución local</span><span class="sxs-lookup"><span data-stu-id="20caf-109">Remote vs. Local Execution</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)  
 <span data-ttu-id="20caf-110">Explica cómo especificar donde desea que se ejecute una consulta.</span><span class="sxs-lookup"><span data-stu-id="20caf-110">Explains how to specify where you want your query executed.</span></span>  
  
 [<span data-ttu-id="20caf-111">Carga inmediata y carga diferida</span><span class="sxs-lookup"><span data-stu-id="20caf-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)  
 <span data-ttu-id="20caf-112">Describe cómo especificar cuándo se cargan objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="20caf-112">Describes how to specify when related objects are loaded.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20caf-113">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="20caf-113">Related Sections</span></span>  
 [<span data-ttu-id="20caf-114">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="20caf-114">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="20caf-115">Contiene vínculos a temas que explican la tecnología de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20caf-115">Contains links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology.</span></span>  
  
 [<span data-ttu-id="20caf-116">Identidad de objetos</span><span class="sxs-lookup"><span data-stu-id="20caf-116">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 <span data-ttu-id="20caf-117">Explica el concepto de identidad de objeto en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20caf-117">Explains the concept of object identity in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="20caf-118">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="20caf-118">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="20caf-119">Proporciona una introducción a las operaciones de consulta en [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20caf-119">Provides an introduction to query operations in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
