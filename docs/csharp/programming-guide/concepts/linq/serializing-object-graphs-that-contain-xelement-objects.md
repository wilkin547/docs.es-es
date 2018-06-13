---
title: Serializar gráficos de objeto que contienen objetos XElement (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: f51a026642563e1c1690d9a49220aae462840211
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338912"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="09f95-102">Serializar gráficos de objeto que contienen objetos XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="09f95-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="09f95-103">Este tema presenta la funcionalidad de serializar gráficos de objetos que contienen referencias a objetos de tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="09f95-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="09f95-104">Para facilitar este tipo de serialización, <xref:System.Xml.Linq.XElement> implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="09f95-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="09f95-105">Tenga en cuenta que sólo la clase <xref:System.Xml.Linq.XElement> implementa la serialización.</span><span class="sxs-lookup"><span data-stu-id="09f95-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09f95-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="09f95-106">In This Section</span></span>  
  
|<span data-ttu-id="09f95-107">Tema</span><span class="sxs-lookup"><span data-stu-id="09f95-107">Topic</span></span>|<span data-ttu-id="09f95-108">Description</span><span class="sxs-lookup"><span data-stu-id="09f95-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="09f95-109">[How to: Serialize Using XmlSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md) (Cómo: Serializar con XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="09f95-109">[How to: Serialize Using XmlSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)</span></span>|<span data-ttu-id="09f95-110">Demuestra cómo serializar usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="09f95-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="09f95-111">[How to: Serialize Using DataContractSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md) (Cómo: Serializar con DataContractSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="09f95-111">[How to: Serialize Using DataContractSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)</span></span>|<span data-ttu-id="09f95-112">Demuestra cómo serializar usando <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="09f95-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09f95-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="09f95-113">See Also</span></span>  
 [<span data-ttu-id="09f95-114">Programación avanzada de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="09f95-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
