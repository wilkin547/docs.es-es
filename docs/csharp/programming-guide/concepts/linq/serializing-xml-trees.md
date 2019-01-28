---
title: Serializar árboles XML (C#)
ms.date: 07/20/2015
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
ms.openlocfilehash: a1c39c4c85cbd01fa7c3f3f99f2dfae49e3721d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583449"
---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="10d96-102">Serializar árboles XML (C#)</span><span class="sxs-lookup"><span data-stu-id="10d96-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="10d96-103">Serializar un árbol XML significa generar XML a partir de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="10d96-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="10d96-104">Puede serializarlo en un archivo, en una implementación concreta de la clase <xref:System.IO.TextWriter> o en una implementación concreta de un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="10d96-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="10d96-105">Puede controlar diversos aspectos del proceso de serialización.</span><span class="sxs-lookup"><span data-stu-id="10d96-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="10d96-106">Por ejemplo, puede decidir si desea agregar una sangría al XML serializado y si desea escribe una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="10d96-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10d96-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="10d96-107">In This Section</span></span>  
  
|<span data-ttu-id="10d96-108">Tema</span><span class="sxs-lookup"><span data-stu-id="10d96-108">Topic</span></span>|<span data-ttu-id="10d96-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="10d96-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="10d96-110">Mantener un espacio en blanco al serializar</span><span class="sxs-lookup"><span data-stu-id="10d96-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="10d96-111">Describe cómo controlar el comportamiento de los espacios en blanco a la hora de serializar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="10d96-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="10d96-112">Serializar con una declaración XML (C#)</span><span class="sxs-lookup"><span data-stu-id="10d96-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="10d96-113">Describe cómo serializar un árbol XML que incluya una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="10d96-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="10d96-114">Serializar en archivos, escritores de texto y escritores XML</span><span class="sxs-lookup"><span data-stu-id="10d96-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="10d96-115">Describe cómo serializar un documento en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="10d96-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="10d96-116">Serializar a un objeto XmlReader (invocando XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="10d96-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="10d96-117">Describe cómo crear un <xref:System.Xml.XmlReader> que permita a otro módulo leer los contenidos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="10d96-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10d96-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="10d96-118">See also</span></span>

- [<span data-ttu-id="10d96-119">Guía de programación (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="10d96-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
