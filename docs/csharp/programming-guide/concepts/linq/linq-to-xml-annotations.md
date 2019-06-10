---
title: Anotaciones de LINQ to XML
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: 5f1940be2fc126ff9e9c7a4cb37e5cc7fc95d3c3
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689943"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="919e2-102">Anotaciones de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="919e2-102">LINQ to XML Annotations</span></span>

<span data-ttu-id="919e2-103">Las anotaciones de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permiten asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="919e2-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="919e2-104">Si desea agregar una anotación a un componente XML, como puede ser un <xref:System.Xml.Linq.XElement> o un <xref:System.Xml.Linq.XAttribute>, deberá llamar al método <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="919e2-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="919e2-105">Las anotaciones se obtienen por tipos.</span><span class="sxs-lookup"><span data-stu-id="919e2-105">You retrieve annotations by type.</span></span>

<span data-ttu-id="919e2-106">Tenga en cuenta que las anotaciones no forman parte del conjunto de información de XML, por lo que no se serializan o deserializan.</span><span class="sxs-lookup"><span data-stu-id="919e2-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="919e2-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="919e2-107">Methods</span></span>

<span data-ttu-id="919e2-108">Puede utilizar los siguientes métodos a la hora de trabajar con anotaciones:</span><span class="sxs-lookup"><span data-stu-id="919e2-108">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="919e2-109">Método</span><span class="sxs-lookup"><span data-stu-id="919e2-109">Method</span></span>|<span data-ttu-id="919e2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="919e2-110">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="919e2-111">Agrega un objeto a la lista de anotaciones de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="919e2-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="919e2-112">Obtiene el primer objeto de anotación del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="919e2-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="919e2-113">Obtiene una colección de anotaciones del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="919e2-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="919e2-114">Elimina las anotaciones del tipo especificado de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="919e2-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
