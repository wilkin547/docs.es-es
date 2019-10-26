---
title: Descendants (propiedad dinámica de XElement)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 8d14b0a94d1a2028a56f649a574f157264ba50fa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921183"
---
# <a name="descendants-xelement-dynamic-property"></a><span data-ttu-id="b5289-102">Descendants (propiedad dinámica de XElement)</span><span class="sxs-lookup"><span data-stu-id="b5289-102">Descendants (XElement dynamic property)</span></span>

<span data-ttu-id="b5289-103">Obtiene un indizador que se usa para recuperar todos los descendientes del elemento actual que coinciden con el nombre expandido especificado.</span><span class="sxs-lookup"><span data-stu-id="b5289-103">Gets an indexer used to retrieve all the descendant elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5289-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5289-104">Syntax</span></span>

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="b5289-105">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5289-105">Property value/return value</span></span>

<span data-ttu-id="b5289-106">Un indizador del tipo `IEnumerable<XElement> Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="b5289-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="b5289-107">Este indizador toma el nombre expandido de los elementos descendientes especificados y devuelve los elementos secundarios coincidentes en una colección <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.</span><span class="sxs-lookup"><span data-stu-id="b5289-107">This indexer takes the expanded name of the specified descendant elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5289-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5289-108">Remarks</span></span>

<span data-ttu-id="b5289-109">Esta propiedad es equivalente al método <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> de la clase <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="b5289-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="b5289-110">Los elementos de la colección devuelta están en el orden del documento de origen XML.</span><span class="sxs-lookup"><span data-stu-id="b5289-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="b5289-111">Esta propiedad usa la ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="b5289-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5289-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5289-112">See also</span></span>

- [<span data-ttu-id="b5289-113">Propiedades dinámicas de la clase XElement</span><span class="sxs-lookup"><span data-stu-id="b5289-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="b5289-114">Elements</span><span class="sxs-lookup"><span data-stu-id="b5289-114">Elements</span></span>](elements-xelement-dynamic-property.md)
