---
title: Analizar un documento XML (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d262fd2177ac77ab5109362f94cc51d03c9563c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-xml-c"></a><span data-ttu-id="b6eec-102">Analizar un documento XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b6eec-102">Parsing XML (C#)</span></span>
<span data-ttu-id="b6eec-103">Los temas de esta sección describen cómo analizar documentos XML.</span><span class="sxs-lookup"><span data-stu-id="b6eec-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6eec-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b6eec-104">In This Section</span></span>  
  
|<span data-ttu-id="b6eec-105">Tema</span><span class="sxs-lookup"><span data-stu-id="b6eec-105">Topic</span></span>|<span data-ttu-id="b6eec-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6eec-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6eec-107">[How to: Parse a String (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md) (Cómo: Analizar una cadena (C#))</span><span class="sxs-lookup"><span data-stu-id="b6eec-107">[How to: Parse a String (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)</span></span>|<span data-ttu-id="b6eec-108">Muestra cómo analizar una cadena para crear un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="b6eec-108">Shows how to parse a string to create an XML tree.</span></span>|  
|<span data-ttu-id="b6eec-109">[How to: Load XML from a File (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md) (Cómo: Cargar un documento XML desde un archivo (C#))</span><span class="sxs-lookup"><span data-stu-id="b6eec-109">[How to: Load XML from a File (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)</span></span>|<span data-ttu-id="b6eec-110">Muestra cómo cargar XML desde un identificador URI mediante el método <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6eec-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="b6eec-111">Mantener un espacio en blanco al cargar o analizar XML</span><span class="sxs-lookup"><span data-stu-id="b6eec-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="b6eec-112">Describe cómo controlar el comportamiento de los espacios en blanco de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] al cargar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="b6eec-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|<span data-ttu-id="b6eec-113">[How to: Catch Parsing Errors (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md) (Cómo: Detectar errores de análisis (C#))</span><span class="sxs-lookup"><span data-stu-id="b6eec-113">[How to: Catch Parsing Errors (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)</span></span>|<span data-ttu-id="b6eec-114">Muestra cómo detectar XML no válido o mal formado.</span><span class="sxs-lookup"><span data-stu-id="b6eec-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|<span data-ttu-id="b6eec-115">[How to: Create a Tree from an XmlReader (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md) (Cómo: Crear un árbol a partir de un objeto XmlReader (C#))</span><span class="sxs-lookup"><span data-stu-id="b6eec-115">[How to: Create a Tree from an XmlReader (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)</span></span>|<span data-ttu-id="b6eec-116">Muestra cómo crear un árbol XML directamente de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b6eec-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|<span data-ttu-id="b6eec-117">[How to: Stream XML Fragments from an XmlReader (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md) (Cómo: Hacer streaming de fragmentos XML desde un objeto XmlReader (C#))</span><span class="sxs-lookup"><span data-stu-id="b6eec-117">[How to: Stream XML Fragments from an XmlReader (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)</span></span>|<span data-ttu-id="b6eec-118">Muestra cómo transmitir por secuencias fragmentos XML con <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b6eec-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="b6eec-119">Cuando deba procesar archivos XML de gran tamaño de forma arbitraria, quizás no sea factible cargar la totalidad del árbol XML en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b6eec-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="b6eec-120">En su lugar, puede transmitir por secuencias fragmentos XML.</span><span class="sxs-lookup"><span data-stu-id="b6eec-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6eec-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6eec-121">See Also</span></span>  
 <span data-ttu-id="b6eec-122">[Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md) (Crear árboles XML (C#))</span><span class="sxs-lookup"><span data-stu-id="b6eec-122">[Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)</span></span>
