---
title: '{}Secuencia de escape: extensión de marcado'
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
ms.openlocfilehash: b0646c62a1342eb160d1967e86ac286429013f3c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053873"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="34108-102">Secuencia de escape / extensión de marcado {}</span><span class="sxs-lookup"><span data-stu-id="34108-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="34108-103">Proporciona la secuencia de escape XAML para los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="34108-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="34108-104">La secuencia de escape permite que los valores subsiguientes del atributo se interpreten como un literal.</span><span class="sxs-lookup"><span data-stu-id="34108-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="34108-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="34108-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="34108-106">Uso de elementos de propiedad XAML</span><span class="sxs-lookup"><span data-stu-id="34108-106">XAML Property Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="34108-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="34108-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34108-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="34108-108">*literalValue*</span></span>|<span data-ttu-id="34108-109">Cadena literal que sigue a la secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="34108-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="34108-110">Normalmente, esta cadena contiene una llave de apertura o de cierre ({o}).</span><span class="sxs-lookup"><span data-stu-id="34108-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34108-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34108-111">Remarks</span></span>  
 <span data-ttu-id="34108-112">La secuencia de escape{}() se utiliza para que se pueda usar una llave de apertura ({) como un carácter literal en XAML.</span><span class="sxs-lookup"><span data-stu-id="34108-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="34108-113">Los lectores de XAML suelen usar la llave de apertura ({) para indicar el punto de entrada de una extensión de marcado; sin embargo, primero comprueban el siguiente carácter para determinar si se trata de una llave de cierre (}).</span><span class="sxs-lookup"><span data-stu-id="34108-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="34108-114">Solo cuando las dos llaves ({}) son adyacentes, se consideran una secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="34108-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="34108-115">Si se encuentra la secuencia de escape, el lector XAML debe procesar el resto de la cadena como una cadena.</span><span class="sxs-lookup"><span data-stu-id="34108-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="34108-116">Sin embargo, si la secuencia de escape se aplica a un miembro que tiene un convertidor de tipos, la cadena puede someterse a la conversión de tipos cuando la interpreta un escritor XAML.</span><span class="sxs-lookup"><span data-stu-id="34108-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="34108-117">La secuencia de escape no es una extensión de marcado y no está respaldada por una clase.</span><span class="sxs-lookup"><span data-stu-id="34108-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="34108-118">Sin embargo, es una Convención que los lectores de XAML (incluidos los lectores de XAML personalizados) deben respetar.</span><span class="sxs-lookup"><span data-stu-id="34108-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="34108-119">De esta manera, no se puede usar una comilla (") como secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="34108-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="34108-120">Si tiene que establecer una comilla como valor de propiedad para una propiedad que no sea de contenido, use la sintaxis del elemento de propiedad y coloque la comilla como una cadena dentro del elemento de propiedad, o use una entidad de caracteres XML.</span><span class="sxs-lookup"><span data-stu-id="34108-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="34108-121">En el caso de una propiedad de contenido, la comilla puede ser todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="34108-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="34108-122">La secuencia de escape{}() suele ser necesaria cuando se especifica un tipo XML que debe incluir un calificador de espacio de nombres en una ubicación donde pueda aparecer una extensión de marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="34108-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="34108-123">Esto incluye el inicio de un valor de atributo XAML y en una extensión de marcado, inmediatamente después de un signo igual (=).</span><span class="sxs-lookup"><span data-stu-id="34108-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="34108-124">En el ejemplo siguiente se muestran secuencias de escape para un espacio de nombres XML que aparece al principio de un valor de atributo XAML.</span><span class="sxs-lookup"><span data-stu-id="34108-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="34108-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="34108-125">See also</span></span>

- [<span data-ttu-id="34108-126">Convertidores de tipos y extensiones de marcado para XAML</span><span class="sxs-lookup"><span data-stu-id="34108-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="34108-127">Entidades de caracteres XML y XAML</span><span class="sxs-lookup"><span data-stu-id="34108-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)
