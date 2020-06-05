---
title: LINQ to XML Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: 917129a06483ce2001e178d744440504533d28d6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84369016"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="90d0c-102">Anotaciones de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="90d0c-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="90d0c-103">Las anotaciones de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permiten asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="90d0c-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="90d0c-104">Si desea agregar una anotación a un componente XML, como puede ser un <xref:System.Xml.Linq.XElement> o un <xref:System.Xml.Linq.XAttribute>, deberá llamar al método <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="90d0c-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="90d0c-105">Las anotaciones se obtienen por tipos.</span><span class="sxs-lookup"><span data-stu-id="90d0c-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="90d0c-106">Tenga en cuenta que las anotaciones no forman parte del conjunto de información de XML, por lo que no se serializan o deserializan.</span><span class="sxs-lookup"><span data-stu-id="90d0c-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90d0c-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="90d0c-107">Methods</span></span>  
 <span data-ttu-id="90d0c-108">Puede utilizar los siguientes métodos a la hora de trabajar con anotaciones:</span><span class="sxs-lookup"><span data-stu-id="90d0c-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="90d0c-109">Método</span><span class="sxs-lookup"><span data-stu-id="90d0c-109">Method</span></span>|<span data-ttu-id="90d0c-110">Description</span><span class="sxs-lookup"><span data-stu-id="90d0c-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="90d0c-111">Agrega un objeto a la lista de anotaciones de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="90d0c-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="90d0c-112">Obtiene el primer objeto de anotación del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="90d0c-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="90d0c-113">Obtiene una colección de anotaciones del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="90d0c-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="90d0c-114">Elimina las anotaciones del tipo especificado de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="90d0c-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90d0c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90d0c-115">See also</span></span>

- [<span data-ttu-id="90d0c-116">Programación de LINQ to XML avanzada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90d0c-116">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
