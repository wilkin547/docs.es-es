---
title: Guía de programación
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 0746d14d7be0b67bc9966ae0c5a4af0a3226c1e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546567"
---
# <a name="programming-guide"></a><span data-ttu-id="8d0a1-102">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="8d0a1-102">Programming Guide</span></span>
<span data-ttu-id="8d0a1-103">Esta sección contiene información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d0a1-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="8d0a1-104">Si usa Visual Studio, también puede usar la Object Relational Designer para realizar muchas de estas mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="8d0a1-105">También puede buscar en Microsoft Docs para ver si hay problemas específicos y puede participar en el [Foro de LINQ](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), donde puede discutir con mayor detalle temas más complejos con expertos.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="8d0a1-106">Por último, el [LINQ to SQL: Language-Integrated Query para datos relacionales tecnología de detalles de](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) las notas del producto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , completos con Visual Basic y ejemplos de código de C#.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d0a1-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8d0a1-107">In This Section</span></span>  
 [<span data-ttu-id="8d0a1-108">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="8d0a1-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="8d0a1-109">Describe cómo generar un modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="8d0a1-110">Comunicarse con la base de datos</span><span class="sxs-lookup"><span data-stu-id="8d0a1-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="8d0a1-111">Describe cómo utilizar un objeto <xref:System.Data.Linq.DataContext> como canal de comunicación con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="8d0a1-112">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="8d0a1-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="8d0a1-113">Describe cómo ejecutar consultas en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona muchos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="8d0a1-114">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="8d0a1-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="8d0a1-115">Describe cómo cambiar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="8d0a1-116">Capacidad de depuración</span><span class="sxs-lookup"><span data-stu-id="8d0a1-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="8d0a1-117">Describe la compatibilidad disponible para depurar proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d0a1-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="8d0a1-118">Información general</span><span class="sxs-lookup"><span data-stu-id="8d0a1-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="8d0a1-119">Incluye elementos adicionales, como la resolución de conflictos de simultaneidad, la creación de bases de datos, etc., para usuarios más avanzados.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8d0a1-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8d0a1-120">Related Sections</span></span>  
 [<span data-ttu-id="8d0a1-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8d0a1-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="8d0a1-122">Proporciona vínculos a temas donde se explica la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y se muestran sus características.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="8d0a1-123">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8d0a1-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="8d0a1-124">Incluye vínculos a temas que muestran cómo utilizar los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="8d0a1-125">Introducción a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="8d0a1-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="8d0a1-126">Proporciona recursos para ayudarle a empezar a obtener información sobre LINQ to SQL mediante C#.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="8d0a1-127">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d0a1-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="8d0a1-128">Proporciona recursos para ayudarle a empezar a obtener información sobre LINQ to SQL mediante Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8d0a1-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
