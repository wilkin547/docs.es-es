---
title: LINQ to Objects (C#)
description: Obtenga información sobre LINQ to Objects en C#, que usa consultas LINQ con cualquier colección IEnumerable o IEnumerable<T> sin una API o proveedor LINQ intermedios.
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 575708f14487670a4371d470dcdcf650b03c3175
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202531"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="7d044-103">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-103">LINQ to Objects (C#)</span></span>

<span data-ttu-id="7d044-104">El término "LINQ to Objects" se refiere al uso de consultas LINQ con cualquier colección <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> directamente, sin usar un proveedor o una API de LINQ intermedios como [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](../../../../standard/linq/linq-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d044-104">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](../../../../standard/linq/linq-xml-overview.md).</span></span> <span data-ttu-id="7d044-105">Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="7d044-105">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="7d044-106">La colección puede haberla definido el usuario, o bien puede que la haya devuelto una API de .NET.</span><span class="sxs-lookup"><span data-stu-id="7d044-106">The collection may be user-defined or may be returned by a .NET API.</span></span>  
  
 <span data-ttu-id="7d044-107">Básicamente, LINQ to Objects representa un nuevo enfoque para las colecciones.</span><span class="sxs-lookup"><span data-stu-id="7d044-107">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="7d044-108">En el sistema antiguo, tenía que escribir complejos bucles `foreach` que especificaban cómo recuperar los datos de una colección.</span><span class="sxs-lookup"><span data-stu-id="7d044-108">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="7d044-109">En el enfoque de LINQ, se escribe código declarativo que describe qué se quiere recuperar.</span><span class="sxs-lookup"><span data-stu-id="7d044-109">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="7d044-110">Además, las consultas LINQ ofrecen tres ventajas principales respecto a los bucles `foreach` tradicionales:</span><span class="sxs-lookup"><span data-stu-id="7d044-110">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
- <span data-ttu-id="7d044-111">Son más concisas y legibles, especialmente cuando se filtran varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="7d044-111">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
- <span data-ttu-id="7d044-112">Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.</span><span class="sxs-lookup"><span data-stu-id="7d044-112">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
- <span data-ttu-id="7d044-113">Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="7d044-113">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="7d044-114">Por lo general, cuanto más compleja es la operación que se quiere realizar en los datos, más ventajas se obtienen al usar LINQ en lugar de las técnicas de iteración tradicionales.</span><span class="sxs-lookup"><span data-stu-id="7d044-114">In general, the more complex the operation you want to perform on the data, the more benefit you'll realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="7d044-115">El propósito de esta sección es mostrar el enfoque de LINQ con algunos ejemplos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7d044-115">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="7d044-116">No pretende ser exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="7d044-116">It's not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d044-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7d044-117">In This Section</span></span>  

 [<span data-ttu-id="7d044-118">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-118">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="7d044-119">Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7d044-119">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="7d044-120">También incluye vínculos a artículos que muestran estos principios.</span><span class="sxs-lookup"><span data-stu-id="7d044-120">Also includes links to articles that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="7d044-121">LINQ y reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-121">LINQ and Reflection (C#)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 <span data-ttu-id="7d044-122">Vincula a un ejemplo que muestra cómo usa LINQ la reflexión.</span><span class="sxs-lookup"><span data-stu-id="7d044-122">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="7d044-123">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-123">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="7d044-124">Explica cómo se puede usar LINQ para interactuar con sistemas de archivos.</span><span class="sxs-lookup"><span data-stu-id="7d044-124">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="7d044-125">También incluye vínculos a artículos que muestran estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="7d044-125">Also includes links to articles that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="7d044-126">Procedimiento para consultar un objeto ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-126">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="7d044-127">Muestra cómo consultar un objeto ArrayList en C#.</span><span class="sxs-lookup"><span data-stu-id="7d044-127">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="7d044-128">Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-128">How to add custom methods for LINQ queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="7d044-129">Explica cómo extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7d044-129">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="7d044-130">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7d044-130">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="7d044-131">Proporciona vínculos a artículos que explican LINQ e incluye ejemplos de código que realizan consultas.</span><span class="sxs-lookup"><span data-stu-id="7d044-131">Provides links to articles that explain LINQ and provide examples of code that perform queries.</span></span>
