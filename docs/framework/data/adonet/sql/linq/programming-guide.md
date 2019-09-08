---
title: Guía de programación
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: c33c7749599de0450a9f969e5802485d154a61e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781255"
---
# <a name="programming-guide"></a><span data-ttu-id="3e4d8-102">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="3e4d8-102">Programming Guide</span></span>
<span data-ttu-id="3e4d8-103">Esta sección contiene información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e4d8-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="3e4d8-104">Si usa Visual Studio, también puede usar la Object Relational Designer para realizar muchas de estas mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="3e4d8-105">También puede buscar en Microsoft Docs para ver si hay problemas específicos y puede participar en el [Foro de LINQ](https://go.microsoft.com/fwlink/?LinkId=76488), donde puede discutir con mayor detalle temas más complejos con expertos.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="3e4d8-106">Por último, la tecnología de detalles [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de las notas del producto de los [datos relacionales LINQ to SQL: Language-Integrated Query para datos relacionales](https://go.microsoft.com/fwlink/?LinkId=93205) , junto con Visual Basic y C# ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e4d8-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3e4d8-107">In This Section</span></span>  
 [<span data-ttu-id="3e4d8-108">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="3e4d8-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="3e4d8-109">Describe cómo generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="3e4d8-110">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="3e4d8-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="3e4d8-111">Describe cómo utilizar un objeto <xref:System.Data.Linq.DataContext> como canal de comunicación con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="3e4d8-112">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="3e4d8-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="3e4d8-113">Describe cómo ejecutar consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona muchos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="3e4d8-114">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="3e4d8-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="3e4d8-115">Describe cómo cambiar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="3e4d8-116">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="3e4d8-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="3e4d8-117">Describe la compatibilidad disponible para depurar proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e4d8-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="3e4d8-118">Información general</span><span class="sxs-lookup"><span data-stu-id="3e4d8-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="3e4d8-119">Incluye elementos adicionales, como la resolución de conflictos de simultaneidad, la creación de bases de datos, etc., para usuarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3e4d8-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3e4d8-120">Related Sections</span></span>  
 [<span data-ttu-id="3e4d8-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3e4d8-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="3e4d8-122">Proporciona vínculos a temas donde se explica la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y se muestran sus características.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="3e4d8-123">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="3e4d8-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="3e4d8-124">Incluye vínculos a temas que muestran cómo utilizar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="3e4d8-125">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="3e4d8-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="3e4d8-126">Proporciona recursos para ayudarle a empezar a obtener información sobre C#LINQ to SQL mediante.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="3e4d8-127">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e4d8-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="3e4d8-128">Proporciona recursos para ayudarle a empezar a obtener información sobre LINQ to SQL mediante Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3e4d8-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
