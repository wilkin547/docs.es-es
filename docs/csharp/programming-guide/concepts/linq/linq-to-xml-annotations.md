---
title: Anotaciones de LINQ to XML
description: Aprenda a usar anotaciones en LINQ to XML para asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.
ms.date: 07/20/2015
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
ms.openlocfilehash: e7da666139c10b26de37816693202d96498f52d8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165576"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="399e8-103">Anotaciones de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="399e8-103">LINQ to XML Annotations</span></span>

<span data-ttu-id="399e8-104">Las anotaciones de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permiten asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="399e8-104">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>

<span data-ttu-id="399e8-105">Si desea agregar una anotación a un componente XML, como puede ser un <xref:System.Xml.Linq.XElement> o un <xref:System.Xml.Linq.XAttribute>, deberá llamar al método <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="399e8-105">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="399e8-106">Las anotaciones se obtienen por tipos.</span><span class="sxs-lookup"><span data-stu-id="399e8-106">You retrieve annotations by type.</span></span>

<span data-ttu-id="399e8-107">Tenga en cuenta que las anotaciones no forman parte del conjunto de información de XML, por lo que no se serializan o deserializan.</span><span class="sxs-lookup"><span data-stu-id="399e8-107">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>

## <a name="methods"></a><span data-ttu-id="399e8-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="399e8-108">Methods</span></span>

<span data-ttu-id="399e8-109">Puede utilizar los siguientes métodos a la hora de trabajar con anotaciones:</span><span class="sxs-lookup"><span data-stu-id="399e8-109">You can use the following methods when working with annotations:</span></span>

|<span data-ttu-id="399e8-110">Método</span><span class="sxs-lookup"><span data-stu-id="399e8-110">Method</span></span>|<span data-ttu-id="399e8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="399e8-111">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="399e8-112">Agrega un objeto a la lista de anotaciones de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="399e8-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="399e8-113">Obtiene el primer objeto de anotación del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="399e8-113">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="399e8-114">Obtiene una colección de anotaciones del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="399e8-114">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="399e8-115">Elimina las anotaciones del tipo especificado de un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="399e8-115">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|
