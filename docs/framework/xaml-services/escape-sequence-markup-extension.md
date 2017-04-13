---
title: "{} Escape Sequence / Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "{}"
helpviewer_keywords: 
  - "XAML [XAML Services], quotation mark (")"
  - "{} escape sequence [XAML Services]"
  - "XAML [XAML Services], {} escape sequence"
  - "XAML [XAML Services], escape sequence"
  - "quotation mark (") [XAML Services]"
  - "escape sequence [XAML Services]"
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: 21
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
---
# {} Escape Sequence / Markup Extension
Proporciona la secuencia de escape en XAML para los valores de atributo.  La secuencia de escape permite que los valores subsiguientes del atributo se interpreten como un literal.  
  
## Uso de atributos XAML  
  
```  
<object property="{} literalValue" .../>  
```  
  
## Uso de elementos de propiedad XAML  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|**literalValue**|Cadena literal que sigue a la secuencia de escape.  Esta cadena normalmente contiene una llave de apertura o de cierre \({ o }\).|  
  
## Comentarios  
 La secuencia de escape \({}\) se utiliza para poder usar una llave de apertura \({\) como un carácter literal en XAML.  
  
 Los lectores XAML utilizan normalmente la llave de apertura \({\) para indicar el punto de entrada de una extensión de marcado; sin embargo, primero comprueban el carácter siguiente para determinar si es o no una llave de cierre \(}\).  Las dos llaves \({}\) se consideran una secuencia de escape solamente cuando son adyacentes.  
  
 Si se encuentra la secuencia de escape, el lector XAML debe procesar el resto de la cadena como una cadena.  Sin embargo, si la secuencia de escape se aplica a un miembro que tiene un convertidor de tipos, la cadena podría experimentar la conversión de tipos cuando se va a interpretar por un sistema de escritura XAML.  
  
 La secuencia de escape no es una extensión de marcado y no está respaldada por una clase.  Sin embargo, es una convención que los lectores de XAML \(incluidos los lectores personalizados\) deben respetar.  
  
 Las comillas dobles \("\) no se pueden utilizar como secuencia de escape de esta manera.  Si necesita establecer comillas como un valor de propiedad sin contenido, utilice la sintaxis de elementos de propiedad y coloque las comillas como una cadena dentro del elemento de propiedad, o bien utilice una entidad de caracteres XML.  Para una propiedad de contenido, las comillas pueden constituir la totalidad del contenido.  
  
 La secuencia de escape \({}\) suele requerirse al especificar un tipo XML que debe incluir un calificador del espacio de nombres en una ubicación donde pueda aparecer la extensión de marcado XAML.  Esto incluye el principio de un valor de atributo XAML y, en una extensión de marcado, inmediatamente después de un signo igual \(\=\).  En el ejemplo siguiente se muestran las secuencias de escape para un espacio de nombres XML que aparece al principio de un valor de atributo XAML.  
  
 [!code-xml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## Vea también  
 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)   
 [XML Character Entities and XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)