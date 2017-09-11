---
title: "Crear árboles XML (C#)"
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
ms.assetid: bccc3e0a-c08c-468e-9d30-e075670fdace
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
ms.openlocfilehash: 99b197b86096b803b9732ab2546b23ff59e3e2fe
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="creating-xml-trees-c"></a><span data-ttu-id="1d287-102">Crear árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1d287-102">Creating XML Trees (C#)</span></span>
<span data-ttu-id="1d287-103">Una de las tareas XML más habituales es la construcción de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="1d287-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="1d287-104">Esta sección describe varias formas de crearlos.</span><span class="sxs-lookup"><span data-stu-id="1d287-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d287-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1d287-105">In This Section</span></span>  
  
|<span data-ttu-id="1d287-106">Tema</span><span class="sxs-lookup"><span data-stu-id="1d287-106">Topic</span></span>|<span data-ttu-id="1d287-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d287-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1d287-108">Construcción funcional (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d287-108">Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="1d287-109">Proporciona información general acerca de la construcción funcional en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d287-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="1d287-110">La construcción funcional permite crear el árbol XML total o parcialmente en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="1d287-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="1d287-111">En este tema también se muestra cómo incrustar consultas al construir un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="1d287-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="1d287-112">Crear árboles XML en C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1d287-112">Creating XML Trees in C# (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md)|<span data-ttu-id="1d287-113">Muestra cómo crear árboles en C#.</span><span class="sxs-lookup"><span data-stu-id="1d287-113">Shows how to create trees in C#.</span></span>|  
|[<span data-ttu-id="1d287-114">Diferencias entre clonar y adjuntar (C#)</span><span class="sxs-lookup"><span data-stu-id="1d287-114">Cloning vs. Attaching (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="1d287-115">Demuestra la diferencia entre agregar notas de un árbol XML existente (primero se clonan los nodos y luego se agregan) y agregar nodos sin elemento primario (simplemente se adjuntan).</span><span class="sxs-lookup"><span data-stu-id="1d287-115">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|<span data-ttu-id="1d287-116">[Parsing XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md) (Analizar XML [C#])</span><span class="sxs-lookup"><span data-stu-id="1d287-116">[Parsing XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)</span></span>|<span data-ttu-id="1d287-117">Muestra cómo analizar XML desde varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="1d287-117">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1d287-118"> se superpone a <xref:System.Xml.XmlReader>, que se usa para analizar el código XML.</span><span class="sxs-lookup"><span data-stu-id="1d287-118"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="1d287-119">Cómo: Rellenar un árbol XML con un objeto XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d287-119">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="1d287-120">Muestra cómo rellenar un árbol XML con un elemento <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="1d287-120">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="1d287-121">Cómo: Validar con XSD (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d287-121">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="1d287-122">Muestra cómo validar un árbol XML mediante XSD.</span><span class="sxs-lookup"><span data-stu-id="1d287-122">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="1d287-123">Contenido válido de objetos XElement y XDocument</span><span class="sxs-lookup"><span data-stu-id="1d287-123">Valid Content of XElement and XDocument Objects</span></span>](../../../../csharp/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects3.md)|<span data-ttu-id="1d287-124">Describe los argumentos válidos que se pueden pasar a los constructores y los métodos que se usan para agregar contenido a elementos y documentos.</span><span class="sxs-lookup"><span data-stu-id="1d287-124">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d287-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d287-125">See Also</span></span>  
 [<span data-ttu-id="1d287-126">Guía de programación (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="1d287-126">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

