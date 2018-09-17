---
title: Serializar gráficos de objeto que contienen objetos XElement (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: 2e82165421d31ec234de4806b59565fa675217ef
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45618453"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="794bb-102">Serializar gráficos de objeto que contienen objetos XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="794bb-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="794bb-103">Este tema presenta la funcionalidad de serializar gráficos de objetos que contienen referencias a objetos de tipo <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="794bb-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="794bb-104">Para facilitar este tipo de serialización, <xref:System.Xml.Linq.XElement> implementa la interfaz <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="794bb-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="794bb-105">Tenga en cuenta que sólo la clase <xref:System.Xml.Linq.XElement> implementa la serialización.</span><span class="sxs-lookup"><span data-stu-id="794bb-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="794bb-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="794bb-106">In This Section</span></span>  
  
|<span data-ttu-id="794bb-107">Tema</span><span class="sxs-lookup"><span data-stu-id="794bb-107">Topic</span></span>|<span data-ttu-id="794bb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="794bb-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="794bb-109">[How to: Serialize Using XmlSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md) (Cómo: Serializar con XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="794bb-109">[How to: Serialize Using XmlSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)</span></span>|<span data-ttu-id="794bb-110">Demuestra cómo serializar usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="794bb-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="794bb-111">[How to: Serialize Using DataContractSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md) (Cómo: Serializar con DataContractSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="794bb-111">[How to: Serialize Using DataContractSerializer (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)</span></span>|<span data-ttu-id="794bb-112">Demuestra cómo serializar usando <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="794bb-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="794bb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="794bb-113">See Also</span></span>

- [<span data-ttu-id="794bb-114">Programación avanzada de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="794bb-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
