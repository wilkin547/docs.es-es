---
title: Control de xml:space en XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b8356cdb47b6b834e8d9a6bb84b26445af6d865
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="7ee3c-102">Control de xml:space en XAML</span><span class="sxs-lookup"><span data-stu-id="7ee3c-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="7ee3c-103">El `xml:space` es un atributo definido por el XML que declara el comportamiento del procesamiento de espacios en blanco significativos dentro de un elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="7ee3c-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="7ee3c-104">Este comportamiento es pertinente para todo el contenido (texto interno) incluido dentro del elemento donde `xml:space` se declara y también limita su ámbito a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7ee3c-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7ee3c-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="7ee3c-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="7ee3c-106">\- o -</span><span class="sxs-lookup"><span data-stu-id="7ee3c-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="7ee3c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ee3c-107">Remarks</span></span>  
 <span data-ttu-id="7ee3c-108">La definición de la `xml:space` atributo en XAML que incluye sus dos valores posibles se deriva de `xml:space` tal como se define como un "atributo especial" por especificaciones W3C para XML.</span><span class="sxs-lookup"><span data-stu-id="7ee3c-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="7ee3c-109">El valor predeterminado de la `xml:space` atributo es el valor literal `"default"`.</span><span class="sxs-lookup"><span data-stu-id="7ee3c-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="7ee3c-110">Para el valor `"default"`, o si `xml:space` no se indica en absoluto, el comportamiento de análisis de espacio en blanco significativo es el control de forma predeterminada, tal como se define en el tema [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7ee3c-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="7ee3c-111">Para conservar espacio en blanco en el contenido del elemento de objeto, especifique `xml:space="preserve"` en ese elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="7ee3c-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="7ee3c-112">En la mayoría de interpretaciones, la `xml:space` efectos del atributo y el valor del atributo se limitan a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7ee3c-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="7ee3c-113">Para obtener una explicación completa de procesamiento de espacios en XAML, vea [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7ee3c-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee3c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ee3c-114">See Also</span></span>  
 [<span data-ttu-id="7ee3c-115">Procesamiento de espacios en blanco en XAML</span><span class="sxs-lookup"><span data-stu-id="7ee3c-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="7ee3c-116">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7ee3c-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
