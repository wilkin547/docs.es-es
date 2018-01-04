---
title: "Extensión de marcado RelativeSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ea5d269c3d455a4fbe3a34dca4335e0d8999d80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="relativesource-markupextension"></a>Extensión de marcado RelativeSource
Especifica las propiedades de un <xref:System.Windows.Data.RelativeSource> origen de enlace, que se utiliza dentro de un [extensión de marcado de enlace](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), o al establecer la <xref:System.Windows.Data.Binding.RelativeSource%2A> propiedad de un <xref:System.Windows.Data.Binding> elemento establecido en XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>Uso de atributos XAML (anidados en la extensión de enlace)  
  
```xml  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xml  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`modeEnumValue`|Uno de los siguientes:<br /><br /> -El token de cadena `Self`; se corresponde con un <xref:System.Windows.Data.RelativeSource> tal como se creó con su <xref:System.Windows.Data.RelativeSource.Mode%2A> propiedad establecida en <xref:System.Windows.Data.RelativeSourceMode.Self>.<br />-El token de cadena `TemplatedParent`; se corresponde con un <xref:System.Windows.Data.RelativeSource> tal como se creó con su <xref:System.Windows.Data.RelativeSource.Mode%2A> propiedad establecida en <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.<br />-El token de cadena `PreviousData`; se corresponde con un <xref:System.Windows.Data.RelativeSource> tal como se creó con su <xref:System.Windows.Data.RelativeSource.Mode%2A> propiedad establecida en <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.<br />: Vea a continuación para obtener información sobre `FindAncestor` modo.|  
|`FindAncestor`|El token de cadena `FindAncestor`. Al utilizar este token, se entra en un modo en que `RelativeSource` especifica un tipo de antecesor y, opcionalmente, un nivel del antecesor. Corresponde a un <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|  
|`typeName`|Necesario para el modo `FindAncestor`. El nombre de un tipo, que rellena la propiedad <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|  
|`intLevel`|Opcional para el modo `FindAncestor`. Un nivel del antecesor (se evalúa en la dirección del elemento primario en el árbol lógico).|  
  
## <a name="remarks"></a>Comentarios  
 `{RelativeSource TemplatedParent}`usos de enlace son una técnica de clave que dirige a un concepto más grande de la separación de interfaz de usuario de un control y la lógica de un control. Esto permite enlazar desde dentro de la definición de plantilla al elemento primario con plantilla (instancia de objeto en tiempo de ejecución donde se aplica la plantilla). En este caso, el [extensión de marcado TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) es, de hecho, un método abreviado para la siguiente expresión de enlace: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding`o `{RelativeSource TemplatedParent}` usos son solo es relevante en el XAML que define una plantilla. Para obtener más información, vea [extensión de marcado TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)  
  
 `{RelativeSource FindAncestor}`se utiliza principalmente en plantillas de control o predicción composiciones de interfaz de usuario independientes, para los casos donde un control siempre debe estar en un árbol visual de un determinado tipo de antecesor. Por ejemplo, los elementos de un control de elementos pueden usar `FindAncestor` para enlazar a propiedades del antecesor del elemento primario del control de elementos. O bien los elementos que forman parte de la composición de controles en una plantilla pueden usar enlaces `FindAncestor` a los elementos primarios en esa misma estructura de composición.  
  
 En la sintaxis de elementos de objeto para el modo `FindAncestor` que se muestra en las secciones sobre sintaxis XAML, la segunda sintaxis de elementos de objeto se emplea específicamente para el modo `FindAncestor`. El modo `FindAncestor` necesita un valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. Debe establecer <xref:System.Windows.Data.RelativeSource.AncestorType%2A> como un atributo que utiliza un [extensión de marcado x: Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md) referencia al tipo del antecesor para buscar. Se utiliza el valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A> al procesar la solicitud de enlace en tiempo de ejecución.  
  
 Para el modo `FindAncestor`, la propiedad <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> opcional puede ayudar a eliminar la ambigüedad en la búsqueda del antecesor en aquellos casos en que sea posible que exista más de un antecesor de ese tipo en el árbol de elementos.  
  
 Para obtener más información sobre cómo usar el modo `FindAncestor`, vea <xref:System.Windows.Data.RelativeSource>.  
  
 `{RelativeSource Self}`es útil en escenarios donde una propiedad de una instancia debe dependen del valor de otra propiedad de la misma instancia y no tiene relación de propiedad de dependencia general (por ejemplo, la conversión) ya existe entre esas dos propiedades. Aunque es poco probable que dos propiedades existen en un objeto de forma que los valores son idénticos literalmente (y se escriben de forma idéntica), también puede aplicar un `Converter` parámetro a un enlace que tiene `{RelativeSource Self}`y use el convertidor para convertir entre el origen y tipos de destino. Otro escenario para `{RelativeSource Self}` es como parte de un <xref:System.Windows.MultiDataTrigger>.  
  
 Por ejemplo, el código XAML siguiente define un elemento <xref:System.Windows.Shapes.Rectangle> de forma que, independientemente del valor que se especifique para <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sea siempre un cuadrado: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}`es útil en las plantillas de datos, o en aquellos casos donde los enlaces utilicen una colección como origen de datos. Puede usar `{RelativeSource PreviousData}` para resaltar las relaciones entre elementos de datos adyacentes en la colección. Una técnica relacionada es establecer un objeto <xref:System.Windows.Data.MultiBinding> entre los elementos actual y anterior del origen de datos, y utilizar un convertidor en dicho enlace para determinar la diferencia entre ambos elementos y sus propiedades.  
  
 En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> de la plantilla de elementos muestra el número actual. El segundo <xref:System.Windows.Controls.TextBlock> enlace es un <xref:System.Windows.Data.MultiBinding> intervalo nominal que tiene dos <xref:System.Windows.Data.Binding> consistuents: el registro actual y un enlace que usa deliberadamente el registro de datos anterior mediante `{RelativeSource PreviousData}`. A continuación, un convertidor en el objeto <xref:System.Windows.Data.MultiBinding> calcula la diferencia y la devuelve al enlace.  
  
```xml  
<ListBox Name="fibolist">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <StackPanel Orientation="Horizontal">  
            <TextBlock Text="{Binding}"/>  
            <TextBlock>, difference = </TextBlock>  
                <TextBlock>  
                    <TextBlock.Text>  
                        <MultiBinding Converter="{StaticResource DiffConverter}">  
                            <Binding/>  
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>  
                        </MultiBinding>  
                    </TextBlock.Text>  
                </TextBlock>  
            </StackPanel>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
```  
  
 Descripción del enlace de datos como un concepto no se trata aquí, consulte [información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación del procesador XAML, el control para esta extensión de marcado se define por la <xref:System.Windows.Data.RelativeSource> clase.  
  
 `RelativeSource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de XAML utilizan la `{` y `}` caracteres en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe procesar el atributo. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.Binding>  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre declaraciones de enlaces](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [x:Type (extensión de marcado)](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
