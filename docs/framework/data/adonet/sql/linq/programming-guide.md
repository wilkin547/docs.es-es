---
title: Guía de programación
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 542567cf07e86b642a23a879fa6e5476253005b8
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848943"
---
# <a name="programming-guide"></a><span data-ttu-id="f9b65-102">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="f9b65-102">Programming Guide</span></span>
<span data-ttu-id="f9b65-103">Esta sección contiene información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9b65-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="f9b65-104">Si usa Visual Studio, también puede usar el Diseñador relacional de objetos para realizar muchas de estas mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="f9b65-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="f9b65-105">También puede buscar problemas específicos en Microsoft Docs y participar en el [foro LINQ,](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)donde puede discutir temas más complejos en detalle con expertos.</span><span class="sxs-lookup"><span data-stu-id="f9b65-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="f9b65-106">Por último, la tecnología de detalles del documento técnico [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] LINQ to [SQLLINQ to SQL: .NET Language-Integrated Query for Relational Data,](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) completa con ejemplos de código de Visual Basic y C.</span><span class="sxs-lookup"><span data-stu-id="f9b65-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9b65-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f9b65-107">In This Section</span></span>  
 [<span data-ttu-id="f9b65-108">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="f9b65-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="f9b65-109">Describe cómo generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="f9b65-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="f9b65-110">Comunicarse con la base de datos</span><span class="sxs-lookup"><span data-stu-id="f9b65-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="f9b65-111">Describe cómo utilizar un objeto <xref:System.Data.Linq.DataContext> como canal de comunicación con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9b65-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="f9b65-112">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="f9b65-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="f9b65-113">Describe cómo ejecutar consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona muchos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f9b65-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="f9b65-114">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="f9b65-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="f9b65-115">Describe cómo cambiar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9b65-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="f9b65-116">Soporte de depuración</span><span class="sxs-lookup"><span data-stu-id="f9b65-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="f9b65-117">Describe la compatibilidad disponible para depurar proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9b65-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="f9b65-118">Información de antecedentes</span><span class="sxs-lookup"><span data-stu-id="f9b65-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="f9b65-119">Incluye elementos adicionales, como la resolución de conflictos de simultaneidad, la creación de bases de datos, etc., para usuarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="f9b65-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f9b65-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f9b65-120">Related Sections</span></span>  
 [<span data-ttu-id="f9b65-121">LINQ a SQL</span><span class="sxs-lookup"><span data-stu-id="f9b65-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="f9b65-122">Proporciona vínculos a temas donde se explica la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y se muestran sus características.</span><span class="sxs-lookup"><span data-stu-id="f9b65-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="f9b65-123">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="f9b65-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="f9b65-124">Incluye vínculos a temas que muestran cómo utilizar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="f9b65-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="f9b65-125">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="f9b65-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="f9b65-126">Proporciona recursos para ayudarle a empezar a aprender acerca de LINQ to SQLLINQ to SQL mediante C.</span><span class="sxs-lookup"><span data-stu-id="f9b65-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="f9b65-127">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9b65-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="f9b65-128">Proporciona recursos para ayudarle a empezar a aprender acerca de LINQ to SQLLINQ to SQL mediante Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f9b65-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
