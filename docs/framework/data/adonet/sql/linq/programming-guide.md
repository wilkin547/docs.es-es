---
title: "Guía de programación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 431fb89c31e670b6a35a0d8908351a7ea60ce7ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="programming-guide"></a><span data-ttu-id="5adc6-102">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="5adc6-102">Programming Guide</span></span>
<span data-ttu-id="5adc6-103">Esta sección contiene información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5adc6-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="5adc6-104">Si utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], también puede utilizar [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para realizar muchas de estas mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="5adc6-104">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="5adc6-105">También puede buscar Microsoft Docs problemas concretos y participar en la [foro de LINQ](http://go.microsoft.com/fwlink/?LinkId=76488), dónde debatirá detalladamente temas más complejos con expertos.</span><span class="sxs-lookup"><span data-stu-id="5adc6-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="5adc6-106">Por último, en las notas del producto [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) (LINQ to SQL: consultas integradas en el lenguaje .NET para datos relacionales) se explica con detalle la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], junto con ejemplos de código de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] y C#.</span><span class="sxs-lookup"><span data-stu-id="5adc6-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5adc6-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5adc6-107">In This Section</span></span>  
 [<span data-ttu-id="5adc6-108">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="5adc6-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="5adc6-109">Describe cómo generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="5adc6-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="5adc6-110">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="5adc6-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="5adc6-111">Describe cómo utilizar un objeto <xref:System.Data.Linq.DataContext> como canal de comunicación con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5adc6-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="5adc6-112">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="5adc6-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="5adc6-113">Describe cómo ejecutar consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona muchos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5adc6-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="5adc6-114">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="5adc6-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="5adc6-115">Describe cómo cambiar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5adc6-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="5adc6-116">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="5adc6-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="5adc6-117">Describe la compatibilidad disponible para depurar proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5adc6-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="5adc6-118">Información general</span><span class="sxs-lookup"><span data-stu-id="5adc6-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="5adc6-119">Incluye elementos adicionales, como la resolución de conflictos de simultaneidad, la creación de bases de datos, etc., para usuarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="5adc6-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5adc6-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5adc6-120">Related Sections</span></span>  
 [<span data-ttu-id="5adc6-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5adc6-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="5adc6-122">Proporciona vínculos a temas donde se explica la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y se muestran sus características.</span><span class="sxs-lookup"><span data-stu-id="5adc6-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="5adc6-123">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="5adc6-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="5adc6-124">Incluye vínculos a temas que muestran cómo utilizar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="5adc6-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="5adc6-125">Introducción a LINQ</span><span class="sxs-lookup"><span data-stu-id="5adc6-125">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 <span data-ttu-id="5adc6-126">Proporciona recursos para ayudarle a empezar con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5adc6-126">Provides resources to help you begin to learn about [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
