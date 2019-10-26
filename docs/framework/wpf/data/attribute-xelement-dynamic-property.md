---
title: Attribute (propiedad dinámica de XElement)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921207"
---
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="fcd5e-102">Attribute (propiedad dinámica de XElement)</span><span class="sxs-lookup"><span data-stu-id="fcd5e-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="fcd5e-103">Obtiene un indizador que se usa para recuperar la instancia del atributo que se corresponde con el nombre expandido especificado.</span><span class="sxs-lookup"><span data-stu-id="fcd5e-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="fcd5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcd5e-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="fcd5e-105">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fcd5e-105">Property value/return value</span></span>

<span data-ttu-id="fcd5e-106">Un indizador del tipo `XAttribute Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="fcd5e-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="fcd5e-107">Este indizador toma el nombre expandido del atributo especificado y devuelve el elemento <xref:System.Xml.Linq.XAttribute> correspondiente, o bien `null` si no existe ningún atributo con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="fcd5e-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcd5e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fcd5e-108">Remarks</span></span>

<span data-ttu-id="fcd5e-109">Esta propiedad es equivalente al método <xref:System.Xml.Linq.XElement.Attribute%2A> de la clase <xref:System.Xml.Linq.XElement?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="fcd5e-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcd5e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcd5e-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="fcd5e-111">Propiedades dinámicas de la clase XElement</span><span class="sxs-lookup"><span data-stu-id="fcd5e-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="fcd5e-112">Valor</span><span class="sxs-lookup"><span data-stu-id="fcd5e-112">Value</span></span>](value-xattribute-dynamic-property.md)
