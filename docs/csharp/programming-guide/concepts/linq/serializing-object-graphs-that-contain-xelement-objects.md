---
title: "Serializar gráficos de objeto que contienen objetos XElement (C#)"
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
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
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
ms.openlocfilehash: 4e7b1d6365eb27596477de39577caa4144aa3501
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="b0510-102">Serializar gráficos de objeto que contienen objetos XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="b0510-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="b0510-103">Este tema presenta la funcionalidad de serializar gráficos de objetos que contienen referencias a objetos de tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b0510-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="b0510-104">Para facilitar este tipo de serialización, <xref:System.Xml.Linq.XElement> implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="b0510-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="b0510-105">Tenga en cuenta que sólo la clase <xref:System.Xml.Linq.XElement> implementa la serialización.</span><span class="sxs-lookup"><span data-stu-id="b0510-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0510-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b0510-106">In This Section</span></span>  
  
|<span data-ttu-id="b0510-107">Tema</span><span class="sxs-lookup"><span data-stu-id="b0510-107">Topic</span></span>|<span data-ttu-id="b0510-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0510-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b0510-109">[How to: Serialize Using XmlSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md) (Cómo: Serializar con XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="b0510-109">[How to: Serialize Using XmlSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)</span></span>|<span data-ttu-id="b0510-110">Demuestra cómo serializar usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b0510-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="b0510-111">[How to: Serialize Using DataContractSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md) (Cómo: Serializar con DataContractSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="b0510-111">[How to: Serialize Using DataContractSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)</span></span>|<span data-ttu-id="b0510-112">Demuestra cómo serializar usando <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b0510-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0510-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0510-113">See Also</span></span>  
 [<span data-ttu-id="b0510-114">Programación avanzada de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b0510-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

