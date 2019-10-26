---
title: Element (propiedad dinámica de XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921189"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="fdd88-102">Element (propiedad dinámica de XElement)</span><span class="sxs-lookup"><span data-stu-id="fdd88-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="fdd88-103">Obtiene un indizador que se utiliza para recuperar la instancia del elemento secundario que se corresponde con el nombre expandido especificado.</span><span class="sxs-lookup"><span data-stu-id="fdd88-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdd88-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdd88-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="fdd88-105">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fdd88-105">Property value/return value</span></span>

<span data-ttu-id="fdd88-106">Un indizador del tipo `XElement Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="fdd88-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="fdd88-107">Este indizador toma un parámetro de nombre expandido y devuelve el <xref:System.Xml.Linq.XElement> correspondiente, o bien `null` si no existe ningún elemento con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="fdd88-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdd88-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdd88-108">Remarks</span></span>

<span data-ttu-id="fdd88-109">Esta propiedad es equivalente al método <xref:System.Xml.Linq.XContainer.Element%2A> de la clase <xref:System.Xml.Linq.XContainer?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="fdd88-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdd88-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdd88-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="fdd88-111">Propiedades dinámicas de la clase XElement</span><span class="sxs-lookup"><span data-stu-id="fdd88-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="fdd88-112">Elements</span><span class="sxs-lookup"><span data-stu-id="fdd88-112">Elements</span></span>](elements-xelement-dynamic-property.md)
