---
title: '{} Extensión de marcado de la secuencia - de escape'
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
ms.openlocfilehash: 9f6743dd8a82891ac2233978550e5679130de0be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182081"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="05bbb-102">Secuencia de escape / extensión de marcado {}</span><span class="sxs-lookup"><span data-stu-id="05bbb-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="05bbb-103">Proporciona la secuencia de escape XAML para los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="05bbb-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="05bbb-104">La secuencia de escape permite los valores siguientes en el atributo debe interpretarse como un literal.</span><span class="sxs-lookup"><span data-stu-id="05bbb-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="05bbb-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="05bbb-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="05bbb-106">Uso de elementos de propiedad XAML</span><span class="sxs-lookup"><span data-stu-id="05bbb-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="05bbb-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="05bbb-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05bbb-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="05bbb-108">*literalValue*</span></span>|<span data-ttu-id="05bbb-109">La cadena literal que sigue la secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="05bbb-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="05bbb-110">Normalmente, esta cadena contiene una llave de abrir o cerrar ({or}).</span><span class="sxs-lookup"><span data-stu-id="05bbb-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05bbb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05bbb-111">Remarks</span></span>  
 <span data-ttu-id="05bbb-112">La secuencia de escape ({}) se usa para que una llave de apertura ({}) se puede usar como un carácter literal en XAML.</span><span class="sxs-lookup"><span data-stu-id="05bbb-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="05bbb-113">Los lectores XAML normalmente usan la llave de apertura ({}) para indicar el punto de entrada de una extensión de marcado; sin embargo, primero compruebe el siguiente carácter para determinar si se trata de una llave de cierre (}).</span><span class="sxs-lookup"><span data-stu-id="05bbb-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="05bbb-114">Sólo cuando las dos llaves ({}) son adyacente, considera que una secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="05bbb-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="05bbb-115">Si se encuentra la secuencia de escape, el lector XAML debe procesar el resto de la cadena como una cadena.</span><span class="sxs-lookup"><span data-stu-id="05bbb-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="05bbb-116">Sin embargo, si la secuencia de escape se aplica a un miembro que tenga un convertidor de tipos, la cadena podría someterse a una conversión de tipos cuando se interpreta mediante un sistema de escritura XAML.</span><span class="sxs-lookup"><span data-stu-id="05bbb-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="05bbb-117">La secuencia de escape no es una extensión de marcado y no está respaldada por una clase.</span><span class="sxs-lookup"><span data-stu-id="05bbb-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="05bbb-118">Sin embargo, es una convención que se deben respetar los lectores XAML (incluidos los lectores XAML personalizados).</span><span class="sxs-lookup"><span data-stu-id="05bbb-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="05bbb-119">No se puede usar una comilla (") como una secuencia de escape de esta manera.</span><span class="sxs-lookup"><span data-stu-id="05bbb-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="05bbb-120">Si tiene que establecer una comilla como un valor de propiedad para una propiedad sin contenido, use la sintaxis de elemento de propiedad y coloque las comillas como una cadena dentro del elemento de propiedad o usar una entidad de caracteres XML.</span><span class="sxs-lookup"><span data-stu-id="05bbb-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="05bbb-121">Para una propiedad de contenido, las comillas puede ser todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="05bbb-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="05bbb-122">La secuencia de escape ({}) se requiere con frecuencia al especificar un tipo XML que se debe incluir un calificador de espacio de nombres en una ubicación donde podría aparecer una extensión de marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="05bbb-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="05bbb-123">Esto incluye el inicio de un valor de atributo XAML y, en una extensión de marcado, inmediatamente después de un signo igual (=).</span><span class="sxs-lookup"><span data-stu-id="05bbb-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="05bbb-124">El ejemplo siguiente muestra las secuencias de escape para un espacio de nombres XML que aparece al principio de un valor de atributo XAML.</span><span class="sxs-lookup"><span data-stu-id="05bbb-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="05bbb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="05bbb-125">See also</span></span>

- [<span data-ttu-id="05bbb-126">Convertidores de tipos y extensiones de marcado para XAML</span><span class="sxs-lookup"><span data-stu-id="05bbb-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="05bbb-127">Entidades de caracteres XML y XAML</span><span class="sxs-lookup"><span data-stu-id="05bbb-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)
