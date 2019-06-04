---
title: Guía de programación
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 102d2ecba162e19258b707c1c902c29b0a7f2f02
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490050"
---
# <a name="programming-guide"></a><span data-ttu-id="56d34-102">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="56d34-102">Programming Guide</span></span>
<span data-ttu-id="56d34-103">Esta sección contiene información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56d34-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="56d34-104">Si utiliza Visual Studio, también puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para realizar muchas de estas mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="56d34-104">If you are using Visual Studio, you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="56d34-105">También puede buscar Microsoft Docs sobre problemas concretos y participar en el [foro de LINQ](https://go.microsoft.com/fwlink/?LinkId=76488), dónde debatirá detalladamente temas más complejos con expertos.</span><span class="sxs-lookup"><span data-stu-id="56d34-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="56d34-106">Por último, el [LINQ to SQL: Language-Integrated Query para datos relacionales](https://go.microsoft.com/fwlink/?LinkId=93205) notas detalles [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tecnología, junto con ejemplos de código de Visual Basic y C#.</span><span class="sxs-lookup"><span data-stu-id="56d34-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56d34-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56d34-107">In This Section</span></span>  
 [<span data-ttu-id="56d34-108">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="56d34-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="56d34-109">Describe cómo generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="56d34-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="56d34-110">Comunicación con la base de datos</span><span class="sxs-lookup"><span data-stu-id="56d34-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="56d34-111">Describe cómo utilizar un objeto <xref:System.Data.Linq.DataContext> como canal de comunicación con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="56d34-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="56d34-112">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="56d34-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="56d34-113">Describe cómo ejecutar consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona muchos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="56d34-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="56d34-114">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="56d34-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="56d34-115">Describe cómo cambiar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="56d34-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="56d34-116">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="56d34-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="56d34-117">Describe la compatibilidad disponible para depurar proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56d34-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="56d34-118">Información general</span><span class="sxs-lookup"><span data-stu-id="56d34-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="56d34-119">Incluye elementos adicionales, como la resolución de conflictos de simultaneidad, la creación de bases de datos, etc., para usuarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="56d34-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="56d34-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="56d34-120">Related Sections</span></span>  
 [<span data-ttu-id="56d34-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="56d34-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="56d34-122">Proporciona vínculos a temas donde se explica la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y se muestran sus características.</span><span class="sxs-lookup"><span data-stu-id="56d34-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="56d34-123">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="56d34-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="56d34-124">Incluye vínculos a temas que muestran cómo utilizar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="56d34-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="56d34-125">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="56d34-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="56d34-126">Se proporcionan recursos para ayudarle a empezar a obtener información acerca de LINQ a SQL mediante C#.</span><span class="sxs-lookup"><span data-stu-id="56d34-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="56d34-127">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56d34-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="56d34-128">Se proporcionan recursos para ayudarle a empezar a obtener información acerca de LINQ to SQL con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56d34-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
