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
# <a name="-escape-sequence--markup-extension"></a>Secuencia de escape / extensión de marcado {}
Proporciona la secuencia de escape XAML para los valores de atributo. La secuencia de escape permite que los valores subsiguientes del atributo se interpreten como un literal.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Uso de elementos de propiedad XAML  
  
```xaml  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*literalValue*|Cadena literal que sigue a la secuencia de escape. Normalmente, esta cadena contiene una llave de apertura o de cierre ({o}).|  
  
## <a name="remarks"></a>Comentarios  
 La secuencia de escape{}() se utiliza para que se pueda usar una llave de apertura ({) como un carácter literal en XAML.  
  
 Los lectores de XAML suelen usar la llave de apertura ({) para indicar el punto de entrada de una extensión de marcado; sin embargo, primero comprueban el siguiente carácter para determinar si se trata de una llave de cierre (}). Solo cuando las dos llaves ({}) son adyacentes, se consideran una secuencia de escape.  
  
 Si se encuentra la secuencia de escape, el lector XAML debe procesar el resto de la cadena como una cadena. Sin embargo, si la secuencia de escape se aplica a un miembro que tiene un convertidor de tipos, la cadena puede someterse a la conversión de tipos cuando la interpreta un escritor XAML.  
  
 La secuencia de escape no es una extensión de marcado y no está respaldada por una clase. Sin embargo, es una Convención que los lectores de XAML (incluidos los lectores de XAML personalizados) deben respetar.  
  
 De esta manera, no se puede usar una comilla (") como secuencia de escape. Si tiene que establecer una comilla como valor de propiedad para una propiedad que no sea de contenido, use la sintaxis del elemento de propiedad y coloque la comilla como una cadena dentro del elemento de propiedad, o use una entidad de caracteres XML. En el caso de una propiedad de contenido, la comilla puede ser todo el contenido.  
  
 La secuencia de escape{}() suele ser necesaria cuando se especifica un tipo XML que debe incluir un calificador de espacio de nombres en una ubicación donde pueda aparecer una extensión de marcado XAML. Esto incluye el inicio de un valor de atributo XAML y en una extensión de marcado, inmediatamente después de un signo igual (=). En el ejemplo siguiente se muestran secuencias de escape para un espacio de nombres XML que aparece al principio de un valor de atributo XAML.  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>Vea también

- [Convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions-for-xaml.md)
- [Entidades de caracteres XML y XAML](xml-character-entities-and-xaml.md)
