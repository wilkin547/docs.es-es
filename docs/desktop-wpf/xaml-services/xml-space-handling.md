---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432705"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="52f0d-102">Control de xml:space en XAML</span><span class="sxs-lookup"><span data-stu-id="52f0d-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="52f0d-103">El `xml:space` atributo es un atributo definido por XML que declara el comportamiento significativo de procesamiento de espacios en blanco dentro de un elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="52f0d-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="52f0d-104">Este comportamiento es relevante para todo el contenido (texto interno) contenido en el elemento donde `xml:space` se declara y también ámbitos a elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="52f0d-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="52f0d-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="52f0d-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="52f0d-106">\- o -</span><span class="sxs-lookup"><span data-stu-id="52f0d-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="52f0d-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52f0d-107">Remarks</span></span>

<span data-ttu-id="52f0d-108">La definición `xml:space` del atributo en XAML, incluidos `xml:space` sus dos valores posibles, se deriva como definido como un "atributo especial" por las especificaciones W3C para XML.</span><span class="sxs-lookup"><span data-stu-id="52f0d-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="52f0d-109">El valor predeterminado `xml:space` del atributo `"default"`es el valor literal .</span><span class="sxs-lookup"><span data-stu-id="52f0d-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="52f0d-110">Para el `"default"`valor `xml:space` , o si no se indica en absoluto, el comportamiento del análisis de espacios en blanco significativo es el control predeterminado, tal como se define en el tema Procesamiento de espacio en [blanco en XAML](white-space-processing.md).</span><span class="sxs-lookup"><span data-stu-id="52f0d-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="52f0d-111">Para conservar el espacio en `xml:space="preserve"` blanco dentro del contenido del elemento de objeto, especifique en ese elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="52f0d-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="52f0d-112">En la mayoría `xml:space` de las interpretaciones, los efectos de atributo y el valor del atributo se limitan a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="52f0d-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="52f0d-113">Para obtener una explicación completa del procesamiento de espacios en blanco en XAML, vea [Procesamiento de espacio en blanco en XAML](white-space-processing.md).</span><span class="sxs-lookup"><span data-stu-id="52f0d-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52f0d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52f0d-114">See also</span></span>

- [<span data-ttu-id="52f0d-115">Procesamiento de espacios en blanco en XAML</span><span class="sxs-lookup"><span data-stu-id="52f0d-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="52f0d-116">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="52f0d-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
