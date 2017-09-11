---
title: Proyecciones y transformaciones (LINQ to XML) (C#)
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
ms.assetid: bb0457ab-1823-47e6-9d2d-c93c958cc913
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9dc3f97281f2cd13a44e52c441b537e9e2c640a6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="projections-and-transformations-linq-to-xml-c"></a><span data-ttu-id="203b0-102">Proyecciones y transformaciones (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-102">Projections and Transformations (LINQ to XML) (C#)</span></span>
<span data-ttu-id="203b0-103">En esta sección se proporcionan ejemplos de proyecciones y transformaciones [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203b0-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="203b0-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="203b0-104">In This Section</span></span>  
  
|<span data-ttu-id="203b0-105">Tema</span><span class="sxs-lookup"><span data-stu-id="203b0-105">Topic</span></span>|<span data-ttu-id="203b0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="203b0-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="203b0-107">Cómo: Trabajar con diccionarios mediante LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-107">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="203b0-108">Muestra cómo transformar diccionarios en XML, y cómo transformar XML en diccionarios.</span><span class="sxs-lookup"><span data-stu-id="203b0-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="203b0-109">Cómo: Transformar la forma de un árbol XML (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-109">How to: Transform the Shape of an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="203b0-110">Muestra cómo transformar la forma de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="203b0-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="203b0-111">Cómo: Controlar el tipo de una proyección (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-111">How to: Control the Type of a Projection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="203b0-112">Muestra cómo controlar el tipo de una consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203b0-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="203b0-113">Cómo: Proyectar un nuevo tipo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-113">How to: Project a New Type (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="203b0-114">Muestra cómo proyectar la colección de un tipo definido por el usuario desde una consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203b0-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="203b0-115">Cómo: Proyectar un gráfico de objetos (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-115">How to: Project an Object Graph (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="203b0-116">Muestra cómo proyectar un gráfico de objeto más complejo desde una consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203b0-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="203b0-117">Cómo: Proyectar un tipo anónimo (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-117">How to: Project an Anonymous Type (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="203b0-118">Muestra cómo proyectar la colección de objetos anónimos desde una consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203b0-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="203b0-119">Cómo: Generar archivos de texto a partir de XML (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-119">How to: Generate Text Files from XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="203b0-120">Muestra cómo transformar un archivo XML en un archivo de texto no XML.</span><span class="sxs-lookup"><span data-stu-id="203b0-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="203b0-121">Cómo: Generar XML a partir de archivos CSV (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-121">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="203b0-122">Muestra cómo usar [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] para analizar un archivo CSV y generar XML a partir de él.</span><span class="sxs-lookup"><span data-stu-id="203b0-122">Shows how to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="203b0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="203b0-123">See Also</span></span>  
 [<span data-ttu-id="203b0-124">Consultar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="203b0-124">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

