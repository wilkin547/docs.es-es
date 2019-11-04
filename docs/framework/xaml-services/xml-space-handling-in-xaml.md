---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458794"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="b220f-102">Control de xml:space en XAML</span><span class="sxs-lookup"><span data-stu-id="b220f-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="b220f-103">El atributo `xml:space` es un atributo definido por XML que declara el comportamiento de procesamiento de espacios en blanco significativo dentro de un elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="b220f-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="b220f-104">Este comportamiento es relevante para todo el contenido (texto interno) incluido en el elemento en el que se declara `xml:space`, y también se limita a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b220f-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b220f-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="b220f-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="b220f-106">\- o -</span><span class="sxs-lookup"><span data-stu-id="b220f-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="b220f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b220f-107">Remarks</span></span>  
 <span data-ttu-id="b220f-108">La definición del atributo `xml:space` en XAML, incluidos sus dos valores posibles, se deriva de `xml:space` como se define como un "atributo especial" por las especificaciones del W3C para XML.</span><span class="sxs-lookup"><span data-stu-id="b220f-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="b220f-109">El valor predeterminado del atributo `xml:space` es el valor literal `"default"`.</span><span class="sxs-lookup"><span data-stu-id="b220f-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="b220f-110">En el caso del valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento del análisis de espacio en blanco significativo es el control predeterminado, tal y como se define en el tema [procesamiento de espacios en blanco en XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="b220f-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="b220f-111">Para conservar el espacio en blanco dentro del contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="b220f-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="b220f-112">En la mayoría de las interpretaciones, los efectos del atributo `xml:space` y el valor del atributo se limitan a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b220f-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="b220f-113">Para obtener información completa sobre el procesamiento de espacios en blanco en XAML, vea [procesamiento de espacios en blanco en XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="b220f-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b220f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b220f-114">See also</span></span>

- [<span data-ttu-id="b220f-115">Procesamiento de espacios en blanco en XAML</span><span class="sxs-lookup"><span data-stu-id="b220f-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="b220f-116">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="b220f-116">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
