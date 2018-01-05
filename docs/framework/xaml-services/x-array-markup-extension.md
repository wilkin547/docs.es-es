---
title: "x:Array (Extensión de marcado)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc2304ba68956b705904c72e29a17bdac4536c79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xarray-markup-extension"></a>x:Array (Extensión de marcado)
Proporciona compatibilidad general para las matrices de objetos en XAML a través de una extensión de marcado. Esto se corresponde con el `x:ArrayExtension` tipo XAML en [MS-XAML].  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`typeName`|El nombre del tipo que su `x:Array` contendrá. `typeName`puede ser (y a menudo es) como prefijo para un XAML las definiciones de tipo de espacio de nombres que contiene el XAML.|  
|`arrayContents`|El contenido de los elementos que se asigna a la función intrínseca `ArrayExtension.Items` propiedad. Normalmente, estos elementos se especifican como uno o más elementos de objeto dentro de la `x:Array` abriendo y etiquetas de cierre. Objetos especificados aquí se espera que sean asignables al tipo XAML especificado en `typeName`.|  
  
## <a name="remarks"></a>Comentarios  
 `Type`es un atributo necesario para todos los `x:Array` elementos de objeto. A `Type` el valor del parámetro no es necesario usar un `x:Type` extensión de marcado; corto nombre del tipo es un tipo XAML, que se puede especificar como una cadena.  
  
 En la implementación de servicios XAML de .NET Framework, la relación entre el tipo de entrada XAML y la salida CLR <xref:System.Type> de la matriz creada se ve afectado por el contexto de servicio para las extensiones de marcado. La salida <xref:System.Type> es el <xref:System.Xaml.XamlType.UnderlyingType%2A> del tipo XAML de entrada, después de buscar el necesario <xref:System.Xaml.XamlType> basado en el contexto de esquema XAML y el <xref:System.Windows.Markup.IXamlTypeResolver> proporciona el contexto de servicio.  
  
 Cuando se procesa, el contenido de la matriz se asigna a la `ArrayExtension.Items` propiedades intrínsecas. En el <xref:System.Windows.Markup.ArrayExtension> implementación, se representa mediante <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 En la implementación de servicios XAML de .NET Framework, el control para esta extensión de marcado se define mediante la <xref:System.Windows.Markup.ArrayExtension> clase. <xref:System.Windows.Markup.ArrayExtension>no está sellada y podría utilizarse como base para una implementación de extensión de marcado para un tipo de matriz personalizado.  
  
 `x:Array`es que más está diseñado para general la extensibilidad de lenguaje en XAML. Pero `x:Array` también puede ser útil para especificar los valores XAML de ciertas propiedades que aceptan colecciones compatibles con XAML como su contenido estructurado de la propiedad. Por ejemplo, puede especificar el contenido de un <xref:System.Collections.IEnumerable> propiedad con un `x:Array` uso.  
  
 `x:Array` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. `x:Array`parcialmente es una excepción a esta norma porque en lugar de proporcionar el control de valor de atributo alternativos, `x:Array` proporciona un control alternativo de su contenido de texto interno. Este comportamiento permite a los tipos que no pueden ser compatibles con un modelo de contenido existente se agrupan en una matriz y más adelante en el código subyacente al que hace referencia mediante el acceso a la matriz con nombre; puede llamar a <xref:System.Array> métodos para obtener los elementos individuales de la matriz.  
  
 Todas las extensiones de marcado en XAML usan llaves ({,}`)` en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe procesar el valor del atributo. Para obtener más información acerca de las extensiones de marcado en general, vea [convertidores de tipos y extensiones de marcado para XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 En XAML 2009, `x:Array` se define como un lenguaje primitivo en lugar de una extensión de marcado. Para obtener más información, consulte [tipos integrados para primitivas del lenguaje XAML común](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Normalmente, los elementos de objeto que rellenan un `x:Array` no son elementos que existen en el [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres XAML y requieren una asignación de prefijo para un espacio de nombres XAML no predeterminado.  
  
 Por ejemplo, la siguiente es una matriz simple de dos cadenas, con el `sys` prefijo (y también `x`) definidos en el nivel de la matriz.  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Para los tipos personalizados que se usan como elementos de la matriz, la clase también debe admitir los requisitos para que se va a crear instancias en XAML como elementos de objeto. Para obtener más información, consulte [clases XAML y personalizadas para WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>Vea también  
 [Extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Tipos migrados de WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
