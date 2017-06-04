---
title: "x:Array Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Array"
  - "xArray"
helpviewer_keywords: 
  - "x:Array [XAML Services]"
  - "XAML [XAML Services], x:Array markup extension"
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Array Markup Extension
Proporciona compatibilidad general para las matrices de objetos en XAML, a través de una extensión de marcado.  Esto corresponde al tipo XAML `x:ArrayExtension` en \[MS\-XAML\].  
  
## Uso de elementos de objeto XAML  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`typeName`|El nombre del tipo que contendrá su `x:Array`.  `typeName` puede ir precedido \(y a menudo va precedido\) de un espacio de nombres XAML que contiene las definiciones de tipo XAML.|  
|`arrayContents`|El contenido de elementos que se asigna a la propiedad intrínseca `ArrayExtension.Items`.  Normalmente, estos elementos se especifican como uno o más elementos de objeto contenidos dentro de las etiquetas de apertura y cierre `x:Array`.  Se espera que los objetos aquí especificados sean asignables al tipo XAML que se especifica en `typeName`.|  
  
## Comentarios  
 `Type` es un atributo necesario para todos los elementos de objeto `x:Array`.  Un valor de parámetro `Type` no necesita usar una extensión de marcado `x:Type`; el nombre corto del tipo es un tipo XAML que puede especificarse como cadena.  
  
 En la implementación de los servicios XAML de .NET Framework, la relación entre la entrada de tipo XAML y la salida CLR <xref:System.Type> de la matriz creada se ve influida por el contexto de servicio para las extensiones de marcado.  El <xref:System.Type> de salida es el <xref:System.Xaml.XamlType.UnderlyingType%2A> del tipo XAML de entrada, después de buscar el <xref:System.Xaml.XamlType> necesario basado en un contexto de esquema XAML y el servicio <xref:System.Windows.Markup.IXamlTypeResolver> que proporciona el contexto.  
  
 Cuando se procesa, el contenido de la matriz está asignado a la propiedad intrínseca `ArrayExtension.Items`.  En la implementación <xref:System.Windows.Markup.ArrayExtension> , esto es representado por <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=fullName>.  
  
 La clase <xref:System.Windows.Markup.ArrayExtension> define el control para esta extensión de marcado en la implementación de servicios XAML de .NET Framework.  <xref:System.Windows.Markup.ArrayExtension> no es de tipo sealed, y se puede utilizar como base para una implementación de extensión de marcado para un tipo de matriz personalizado.  
  
 `x:Array` está pensada más concretamente para la extensibilidad de lenguaje general en XAML.  No obstante, `x:Array` también puede resultar útil para especificar valores XAML de ciertas propiedades que aceptan colecciones compatibles con XAML como su contenido estructurado de la propiedad.  Por ejemplo, podría especificar el contenido de una propiedad <xref:System.Collections.IEnumerable> con una utilización `x:Array`.  
  
 `x:Array` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  `x:Array` es parcialmente una excepción a esa regla general, porque en lugar de proporcionar un control alternativo de los valores de atributo, `x:Array` proporciona un control alternativo de su contenido de texto interno.  Este comportamiento permite agrupar en una matriz los tipos que podrían no ser compatibles con ningún modelo de contenido existente, y hacer referencia a ellos posteriormente en el código subyacente teniendo acceso a la matriz con nombre; puede llamar a los métodos <xref:System.Array> para obtener los elementos individuales que componen la matriz.  
  
 Todas las extensiones de marcado de XAML usan las llaves \({,}`)` en su sintaxis de atributo, que es la convención que permite que un procesador de XAML reconozca que el valor del atributo se debe procesar mediante una extensión de marcado.  Para obtener más información sobre las extensiones de marcado en general, vea [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 En XAML 2009, `x:Array` se define como un lenguaje primitivo en lugar de una extensión de marcado.  Para obtener más información, vea [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## Notas de uso de WPF  
 Normalmente, los elementos de objeto que rellenan una matriz `x:Array` no suelen existir en el espacio de nombres XAML de [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] y requieren una asignación de prefijo para un espacio de nombres XAML no predeterminado.  
  
 Por ejemplo, a continuación se muestra una matriz simple de dos cadenas, con el prefijo `sys` \(así como `x`\) definido en el nivel de la matriz.  
  
 \[xaml\]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Para los tipos personalizados usados como elementos de matriz, la clase también debe admitir los requisitos para crear instancias de ellos en XAML como elementos de objeto.  Para obtener más información, vea [Clases XAML y personalizadas para WPF](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## Vea también  
 [Extensiones de marcado y XAML de WPF](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)