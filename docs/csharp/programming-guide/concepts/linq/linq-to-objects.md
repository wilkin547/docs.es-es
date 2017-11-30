---
title: LINQ to Objects (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bb2a6593b02125478f2221a6822dec447921c4f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="b1afd-102">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-102">LINQ to Objects (C#)</span></span>
<span data-ttu-id="b1afd-103">El término "LINQ to Objects" se refiere al uso de consultas LINQ con cualquier colección <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> directamente, sin usar un proveedor o una API de LINQ intermedios como [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) o [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="b1afd-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) or [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="b1afd-104">Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="b1afd-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="b1afd-105">La colección puede ser definida por el usuario o haber sido devuelta por una API de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1afd-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="b1afd-106">Básicamente, LINQ to Objects representa un nuevo enfoque para las colecciones.</span><span class="sxs-lookup"><span data-stu-id="b1afd-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="b1afd-107">En el sistema antiguo, tenía que escribir complejos bucles `foreach` que especificaban cómo recuperar los datos de una colección.</span><span class="sxs-lookup"><span data-stu-id="b1afd-107">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="b1afd-108">En el enfoque de LINQ, se escribe código declarativo que describe qué se quiere recuperar.</span><span class="sxs-lookup"><span data-stu-id="b1afd-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="b1afd-109">Además, las consultas LINQ ofrecen tres ventajas principales respecto a los bucles `foreach` tradicionales:</span><span class="sxs-lookup"><span data-stu-id="b1afd-109">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
1.  <span data-ttu-id="b1afd-110">Son más concisas y legibles, especialmente cuando se filtran varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="b1afd-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="b1afd-111">Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.</span><span class="sxs-lookup"><span data-stu-id="b1afd-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="b1afd-112">Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="b1afd-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="b1afd-113">Por lo general, cuanto más compleja sea la operación que quiere realizar en los datos, más ventajas obtendrá al usar LINQ en lugar de las técnicas de iteración tradicionales.</span><span class="sxs-lookup"><span data-stu-id="b1afd-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="b1afd-114">El propósito de esta sección es mostrar el enfoque de LINQ con algunos ejemplos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="b1afd-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="b1afd-115">No pretende ser exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="b1afd-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1afd-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b1afd-116">In This Section</span></span>  
 [<span data-ttu-id="b1afd-117">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-117">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="b1afd-118">Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b1afd-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="b1afd-119">También incluye vínculos a temas que muestran estos principios.</span><span class="sxs-lookup"><span data-stu-id="b1afd-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="b1afd-120">LINQ y reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-120">LINQ and Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="b1afd-121">Vincula a un ejemplo que muestra cómo usa LINQ la reflexión.</span><span class="sxs-lookup"><span data-stu-id="b1afd-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="b1afd-122">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-122">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="b1afd-123">Explica cómo se puede usar LINQ para interactuar con sistemas de archivos.</span><span class="sxs-lookup"><span data-stu-id="b1afd-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="b1afd-124">También incluye vínculos a temas que muestran estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="b1afd-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="b1afd-125">Consultar un objeto ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-125">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="b1afd-126">Muestra cómo consultar un objeto ArrayList en C#.</span><span class="sxs-lookup"><span data-stu-id="b1afd-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="b1afd-127">Agregar métodos personalizados para las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-127">How to: Add Custom Methods for LINQ Queries (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="b1afd-128">Explica cómo extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b1afd-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="b1afd-129">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b1afd-129">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="b1afd-130">Proporciona vínculos a temas que explican LINQ y que proporcionan ejemplos de código que realizan consultas.</span><span class="sxs-lookup"><span data-stu-id="b1afd-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
