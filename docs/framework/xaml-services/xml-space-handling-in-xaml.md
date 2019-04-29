---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: d15bab1ad9234959048fa7b7c3fa2bbbeca5fe6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938728"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="fab3c-102">Control de xml:space en XAML</span><span class="sxs-lookup"><span data-stu-id="fab3c-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="fab3c-103">El `xml:space` es un atributo definido por el XML que declara el comportamiento de procesamiento de espacios en blanco significativos dentro de un elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="fab3c-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="fab3c-104">Este comportamiento es relevante para todo el contenido (texto interno) incluido dentro del elemento donde `xml:space` se declara y también limita su ámbito a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fab3c-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fab3c-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="fab3c-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="fab3c-106">\- o -</span><span class="sxs-lookup"><span data-stu-id="fab3c-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="fab3c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fab3c-107">Remarks</span></span>  
 <span data-ttu-id="fab3c-108">La definición de la `xml:space` se deriva de atributo en XAML, incluidos sus dos valores posibles `xml:space` tal como se define como un "atributo especial" por las especificaciones de W3C para XML.</span><span class="sxs-lookup"><span data-stu-id="fab3c-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="fab3c-109">El valor predeterminado de la `xml:space` atributo es el valor literal `"default"`.</span><span class="sxs-lookup"><span data-stu-id="fab3c-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="fab3c-110">Para el valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento de análisis de espacio en blanco significativo es el control predeterminado, tal como se define en el tema [espacio en blanco en XAML de procesamiento](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="fab3c-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="fab3c-111">Para conservar espacio en blanco dentro del contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="fab3c-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="fab3c-112">En la mayoría de las interpretaciones el `xml:space` efectos del atributo y el valor del atributo se limitan a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fab3c-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="fab3c-113">Para obtener una explicación completa de espacio en blanco en XAML de procesamiento, vea [espacio en blanco en XAML de procesamiento](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="fab3c-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab3c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab3c-114">See also</span></span>

- [<span data-ttu-id="fab3c-115">Espacio en blanco en XAML de procesamiento</span><span class="sxs-lookup"><span data-stu-id="fab3c-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="fab3c-116">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="fab3c-116">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
