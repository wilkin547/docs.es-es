---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 051cb6b3a314509e9593ee570fd659098670e88b
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925862"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="fbd19-102">Control de xml:space en XAML</span><span class="sxs-lookup"><span data-stu-id="fbd19-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="fbd19-103">El `xml:space` es un atributo definido por el XML que declara el comportamiento de procesamiento de espacios en blanco significativos dentro de un elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="fbd19-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="fbd19-104">Este comportamiento es relevante para todo el contenido (texto interno) incluido dentro del elemento donde `xml:space` se declara y también limita su ámbito a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fbd19-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fbd19-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="fbd19-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="fbd19-106">\- o -</span><span class="sxs-lookup"><span data-stu-id="fbd19-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="fbd19-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbd19-107">Remarks</span></span>  
 <span data-ttu-id="fbd19-108">La definición de la `xml:space` se deriva de atributo en XAML, incluidos sus dos valores posibles `xml:space` tal como se define como un "atributo especial" por las especificaciones de W3C para XML.</span><span class="sxs-lookup"><span data-stu-id="fbd19-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="fbd19-109">El valor predeterminado de la `xml:space` atributo es el valor literal `"default"`.</span><span class="sxs-lookup"><span data-stu-id="fbd19-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="fbd19-110">Para el valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento de análisis de espacio en blanco significativo es el control predeterminado, tal como se define en el tema [espacio en blanco en XAML de procesamiento](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="fbd19-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="fbd19-111">Para conservar espacio en blanco dentro del contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="fbd19-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="fbd19-112">En la mayoría de las interpretaciones el `xml:space` efectos del atributo y el valor del atributo se limitan a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fbd19-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="fbd19-113">Para obtener una explicación completa de espacio en blanco en XAML de procesamiento, vea [espacio en blanco en XAML de procesamiento](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="fbd19-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd19-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbd19-114">See Also</span></span>  
 [<span data-ttu-id="fbd19-115">Espacio en blanco en XAML de procesamiento</span><span class="sxs-lookup"><span data-stu-id="fbd19-115">White-space processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="fbd19-116">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="fbd19-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
