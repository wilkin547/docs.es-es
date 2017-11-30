---
title: "Secuencia de escape {}: extensión de marcado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: "21"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: befbf9960afffcd30bc96863dcc00b4acad2c21a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="b6e01-102">Secuencia de escape / extensión de marcado {}</span><span class="sxs-lookup"><span data-stu-id="b6e01-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="b6e01-103">Proporciona la secuencia de escape XAML para los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="b6e01-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="b6e01-104">La secuencia de escape permite los valores siguientes en el atributo debe interpretarse como un literal.</span><span class="sxs-lookup"><span data-stu-id="b6e01-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b6e01-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="b6e01-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="b6e01-106">Uso de elementos de propiedad XAML</span><span class="sxs-lookup"><span data-stu-id="b6e01-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b6e01-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="b6e01-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6e01-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="b6e01-108">*literalValue*</span></span>|<span data-ttu-id="b6e01-109">La cadena literal que sigue la secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="b6e01-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="b6e01-110">Normalmente, esta cadena contiene una llave de abrir o cerrar ({o}).</span><span class="sxs-lookup"><span data-stu-id="b6e01-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6e01-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6e01-111">Remarks</span></span>  
 <span data-ttu-id="b6e01-112">La secuencia de escape ({}) se utiliza para que pueda usarse una llave de apertura ({}) como un carácter literal en XAML.</span><span class="sxs-lookup"><span data-stu-id="b6e01-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="b6e01-113">Los lectores XAML normalmente use la llave de apertura ({}) para indicar el punto de entrada de una extensión de marcado; sin embargo, primero compruebe el siguiente carácter para determinar si se trata de una llave de cierre (}).</span><span class="sxs-lookup"><span data-stu-id="b6e01-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="b6e01-114">Solo si las dos llaves ({}) son adyacentes, se consideran que una secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="b6e01-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="b6e01-115">Si se encuentra la secuencia de escape, el lector XAML debería procesar el resto de la cadena como una cadena.</span><span class="sxs-lookup"><span data-stu-id="b6e01-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="b6e01-116">Sin embargo, si la secuencia de escape se aplica a un miembro que tenga un convertidor de tipos, la cadena podría someterse a una conversión de tipos cuando se interpreta mediante un escritor de XAML.</span><span class="sxs-lookup"><span data-stu-id="b6e01-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="b6e01-117">La secuencia de escape no es una extensión de marcado y no está respaldada por una clase.</span><span class="sxs-lookup"><span data-stu-id="b6e01-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="b6e01-118">Sin embargo, es una convención que deben respetar los lectores XAML (incluidos los lectores XAML personalizados).</span><span class="sxs-lookup"><span data-stu-id="b6e01-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="b6e01-119">No se puede usar un signo de comillas (") como una secuencia de escape de esta manera.</span><span class="sxs-lookup"><span data-stu-id="b6e01-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="b6e01-120">Si tiene que establecer un signo de comillas como un valor de propiedad para una propiedad sin contenido, usar la sintaxis de elemento de propiedad y coloque las comillas como una cadena dentro del elemento de propiedad o usar una entidad de caracteres XML.</span><span class="sxs-lookup"><span data-stu-id="b6e01-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="b6e01-121">Para una propiedad de contenido, las comillas pueden ser todo el contenido.</span><span class="sxs-lookup"><span data-stu-id="b6e01-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="b6e01-122">La secuencia de escape ({}) se suele ser necesaria cuando se especifica un tipo XML que debe incluir un calificador de espacio de nombres en una ubicación donde puede aparecer una extensión de marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="b6e01-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="b6e01-123">Esto incluye el inicio de un valor de atributo XAML y en una extensión de marcado, inmediatamente después de un signo igual (=).</span><span class="sxs-lookup"><span data-stu-id="b6e01-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="b6e01-124">El ejemplo siguiente muestra las secuencias de escape para un espacio de nombres XML que aparece al principio de un valor de atributo XAML.</span><span class="sxs-lookup"><span data-stu-id="b6e01-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="b6e01-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6e01-125">See Also</span></span>  
 [<span data-ttu-id="b6e01-126">Convertidores de tipos y extensiones de marcado para XAML</span><span class="sxs-lookup"><span data-stu-id="b6e01-126">Type Converters and Markup Extensions for XAML</span></span>](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [<span data-ttu-id="b6e01-127">Entidades de caracteres XML y XAML</span><span class="sxs-lookup"><span data-stu-id="b6e01-127">XML Character Entities and XAML</span></span>](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
