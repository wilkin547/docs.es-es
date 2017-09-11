---
title: "LINQ to ADO.NET (Página de portal)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d768d5796e5eb7ff4fed071d906c672b83b42d2b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="ab54b-102">LINQ to ADO.NET (Página de portal)</span><span class="sxs-lookup"><span data-stu-id="ab54b-102">LINQ to ADO.NET (Portal Page)</span></span>
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)]<span data-ttu-id="ab54b-103"> permite consultar sobre cualquier objeto enumerable de [!INCLUDE[vstecado](~/includes/vstecado-md.md)] mediante el modelo de programación de [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab54b-103"> enables you to query over any enumerable object in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] by using the [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] programming model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab54b-104">La documentación de [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] se encuentra en la sección ADO.NET del SDK de .NET Framework: [LINQ y ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span><span class="sxs-lookup"><span data-stu-id="ab54b-104">The [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span></span>  
  
 <span data-ttu-id="ab54b-105">Existen tres tecnologías [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] de ADO.NET independientes: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] y [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab54b-105">There are three separate ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] technologies: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="ab54b-106"> proporciona consultas más ricas y optimizadas de <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] permite consultar directamente los esquemas de base de datos de [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] y [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] permite consultar un [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab54b-106"> provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] enables you to directly query [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] database schemas, and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] allows you to query an [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="ab54b-107">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ab54b-107">LINQ to DataSet</span></span>  
 <span data-ttu-id="ab54b-108"><xref:System.Data.DataSet> es uno de los componentes más usados de [!INCLUDE[vstecado](~/includes/vstecado-md.md)], además de un elemento clave del modelo de programación desconectado en el que se basa [!INCLUDE[vstecado](~/includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab54b-108">The <xref:System.Data.DataSet> is one of the most widely used components in [!INCLUDE[vstecado](~/includes/vstecado-md.md)], and is a key element of the disconnected programming model that [!INCLUDE[vstecado](~/includes/vstecado-md.md)] is built on.</span></span> <span data-ttu-id="ab54b-109">En cambio, a pesar de su importancia, <xref:System.Data.DataSet> tiene funciones de consulta limitadas.</span><span class="sxs-lookup"><span data-stu-id="ab54b-109">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="ab54b-110"> le permite compilar funciones de consulta más complejas en <xref:System.Data.DataSet> mediante la misma función de consulta disponible para muchos otros orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="ab54b-110"> enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="ab54b-111">Para más información, vea [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ab54b-111">For more information, see [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="ab54b-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ab54b-112">LINQ to SQL</span></span>  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="ab54b-113"> proporciona una infraestructura en tiempo de ejecución para administrar los datos relacionales como objetos.</span><span class="sxs-lookup"><span data-stu-id="ab54b-113"> provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="ab54b-114">En [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], el modelo de datos de una base de datos relacional se asigna a un modelo de objetos expresado en el lenguaje de programación del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="ab54b-114">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="ab54b-115">Cuando se ejecuta la aplicación, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] convierte a SQL las consultas integradas en el lenguaje en el modelo de objetos y las envía a la base de datos para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="ab54b-115">When you execute the application, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="ab54b-116">Cuando la base de datos devuelve los resultados, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] los vuelve a convertir en objetos que se pueden manipular.</span><span class="sxs-lookup"><span data-stu-id="ab54b-116">When the database returns the results, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="ab54b-117"> incluye compatibilidad con los procedimientos almacenados y las funciones definidas por el usuario de la base de datos, además de con la herencia en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="ab54b-117"> includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="ab54b-118">Para más información, vea [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span><span class="sxs-lookup"><span data-stu-id="ab54b-118">For more information, see [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="ab54b-119">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ab54b-119">LINQ to Entities</span></span>  
 <span data-ttu-id="ab54b-120">A través de [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], los datos relacionales se exponen como objetos en el entorno .NET.</span><span class="sxs-lookup"><span data-stu-id="ab54b-120">Through the [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="ab54b-121">Esto hace de la capa de objetos un objetivo idóneo para la compatibilidad con [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], ya que permite a los programadores formular consultas en la base de datos con el lenguaje usado para compilar la lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="ab54b-121">This makes the object layer an ideal target for [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="ab54b-122">Esta función se conoce como [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab54b-122">This capability is known as [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> <span data-ttu-id="ab54b-123">Para más información, vea [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="ab54b-123">See [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab54b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab54b-124">See Also</span></span>  
 <span data-ttu-id="ab54b-125">[LINQ y ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span><span class="sxs-lookup"><span data-stu-id="ab54b-125">[LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span></span>  
 [<span data-ttu-id="ab54b-126">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ab54b-126">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)

