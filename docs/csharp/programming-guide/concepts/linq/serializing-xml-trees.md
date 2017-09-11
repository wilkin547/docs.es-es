---
title: "Serializar árboles XML (C#)"
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
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
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
ms.openlocfilehash: f3b8ee68065a056cccbf02d96bf5f21e7ccea16b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="ca7ff-102">Serializar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="ca7ff-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="ca7ff-103">Serializar un árbol XML significa generar XML a partir de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="ca7ff-104">Puede serializarlo en un archivo, en una implementación concreta de la clase <xref:System.IO.TextWriter> o en una implementación concreta de un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="ca7ff-105">Puede controlar diversos aspectos del proceso de serialización.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="ca7ff-106">Por ejemplo, puede decidir si desea agregar una sangría al XML serializado y si desea escribe una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca7ff-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ca7ff-107">In This Section</span></span>  
  
|<span data-ttu-id="ca7ff-108">Tema</span><span class="sxs-lookup"><span data-stu-id="ca7ff-108">Topic</span></span>|<span data-ttu-id="ca7ff-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca7ff-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ca7ff-110">Mantener un espacio en blanco al serializar</span><span class="sxs-lookup"><span data-stu-id="ca7ff-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="ca7ff-111">Describe cómo controlar el comportamiento de los espacios en blanco a la hora de serializar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="ca7ff-112">Serializar con una declaración XML (C#)</span><span class="sxs-lookup"><span data-stu-id="ca7ff-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="ca7ff-113">Describe cómo serializar un árbol XML que incluya una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="ca7ff-114">Serializar en archivos, escritores de texto y escritores XML</span><span class="sxs-lookup"><span data-stu-id="ca7ff-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="ca7ff-115">Describe cómo serializar un documento en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="ca7ff-116">Serializar a un objeto XmlReader (invocando XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="ca7ff-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="ca7ff-117">Describe cómo crear un <xref:System.Xml.XmlReader> que permita a otro módulo leer los contenidos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="ca7ff-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca7ff-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca7ff-118">See Also</span></span>  
 [<span data-ttu-id="ca7ff-119">Guía de programación (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ca7ff-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

