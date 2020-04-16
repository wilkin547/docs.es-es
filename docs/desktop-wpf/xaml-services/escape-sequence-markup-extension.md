---
title: '{}Secuencia de escape - Extensión de marcado'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432969"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="35f6f-102">{}Secuencia de escape / extensión de marcado</span><span class="sxs-lookup"><span data-stu-id="35f6f-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="35f6f-103">Proporciona la secuencia de escape XAML para los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="35f6f-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="35f6f-104">La secuencia de escape permite que los valores subsiguientes del atributo se interpreten como un literal.</span><span class="sxs-lookup"><span data-stu-id="35f6f-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="35f6f-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="35f6f-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="35f6f-106">Uso de elementos de propiedad XAML</span><span class="sxs-lookup"><span data-stu-id="35f6f-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="35f6f-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="35f6f-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="35f6f-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="35f6f-108">*literalValue*</span></span>|<span data-ttu-id="35f6f-109">Cadena literal que sigue a la secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="35f6f-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="35f6f-110">Normalmente, esta cadena contiene una llave abierta o cercana (o .</span><span class="sxs-lookup"><span data-stu-id="35f6f-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="35f6f-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35f6f-111">Remarks</span></span>

<span data-ttu-id="35f6f-112">La secuencia{}de escape ( ) se usa para que se pueda usar una llave abierta (-) como un carácter literal en XAML.</span><span class="sxs-lookup"><span data-stu-id="35f6f-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="35f6f-113">Los lectores XAML suelen usar la llave abierta para denotar el punto de entrada de una extensión de marcado; sin embargo, primero comprueban el siguiente carácter para determinar si se trata de una llave de cierre.</span><span class="sxs-lookup"><span data-stu-id="35f6f-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="35f6f-114">Sólo cuando las dos{}llaves ( ) son adyacentes, se consideran una secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="35f6f-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="35f6f-115">Si se encuentra la secuencia de escape, el lector XAML debe procesar el resto de la cadena como una cadena.</span><span class="sxs-lookup"><span data-stu-id="35f6f-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="35f6f-116">Sin embargo, si la secuencia de escape se aplica a un miembro que tiene un convertidor de tipos, la cadena podría someterse a la conversión de tipos cuando la interpreta un escritor XAML.</span><span class="sxs-lookup"><span data-stu-id="35f6f-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="35f6f-117">La secuencia de escape no es una extensión de marcado y no está respaldada por una clase.</span><span class="sxs-lookup"><span data-stu-id="35f6f-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="35f6f-118">Sin embargo, es una convención que los lectores XAML (incluidos los lectores XAML personalizados) deben respetar.</span><span class="sxs-lookup"><span data-stu-id="35f6f-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="35f6f-119">Una comilla (") no se puede utilizar como secuencia de escape de esta manera.</span><span class="sxs-lookup"><span data-stu-id="35f6f-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="35f6f-120">Si necesita establecer una comilla como un valor de propiedad para una propiedad noncontent, utilice la sintaxis del elemento de propiedad y coloque la comilla como una cadena dentro del elemento de propiedad o utilice una entidad de caracteres XML.</span><span class="sxs-lookup"><span data-stu-id="35f6f-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="35f6f-121">Para una propiedad de contenido, la comilla puede ser todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="35f6f-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="35f6f-122">La secuencia{}de escape ( ) es frecuentemente necesaria al especificar un tipo XML que debe incluir un calificador de espacio de nombres en una ubicación donde puede aparecer una extensión de marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="35f6f-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="35f6f-123">Esta ubicación incluye el inicio de un valor de atributo XAML y en una extensión de marcado inmediatamente después de un signo igual ( .</span><span class="sxs-lookup"><span data-stu-id="35f6f-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="35f6f-124">En el ejemplo siguiente se muestran las secuencias de escape de un espacio de nombres XML que aparece al principio de un valor de atributo XAML.</span><span class="sxs-lookup"><span data-stu-id="35f6f-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="35f6f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35f6f-125">See also</span></span>

- [<span data-ttu-id="35f6f-126">Convertidores de tipos y extensiones de marcado para XAML</span><span class="sxs-lookup"><span data-stu-id="35f6f-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="35f6f-127">Entidades de caracteres XML y XAML</span><span class="sxs-lookup"><span data-stu-id="35f6f-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
