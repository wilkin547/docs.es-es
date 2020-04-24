---
title: Extensión de marcado RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 6301299da966ade9b5cc7ccd105c8269a486744e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646222"
---
# <a name="relativesource-markupextension"></a>Extensión de marcado RelativeSource

Especifica las propiedades <xref:System.Windows.Data.RelativeSource> de un origen de enlace, que se <xref:System.Windows.Data.Binding.RelativeSource%2A> usará dentro <xref:System.Windows.Data.Binding> de una extensión de [marcado](binding-markup-extension.md)de enlace o al establecer la propiedad de un elemento establecido en XAML.

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
```

o bien

```xml
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
|`modeEnumValue`|Uno de los siguientes:<br /><br /> - el `Self`token de cadena ; corresponde a <xref:System.Windows.Data.RelativeSource> una como <xref:System.Windows.Data.RelativeSource.Mode%2A> creada con <xref:System.Windows.Data.RelativeSourceMode.Self>su propiedad establecida en .<br />- el `TemplatedParent`token de cadena ; corresponde a <xref:System.Windows.Data.RelativeSource> una como <xref:System.Windows.Data.RelativeSource.Mode%2A> creada con <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>su propiedad establecida en .<br />- el `PreviousData`token de cadena ; corresponde a <xref:System.Windows.Data.RelativeSource> una como <xref:System.Windows.Data.RelativeSource.Mode%2A> creada con <xref:System.Windows.Data.RelativeSourceMode.PreviousData>su propiedad establecida en .<br />- Consulte a `FindAncestor` continuación para obtener información sobre el modo.|
|`FindAncestor`|El token de cadena `FindAncestor`. Al utilizar este token, se entra en un modo en que `RelativeSource` especifica un tipo de antecesor y, opcionalmente, un nivel del antecesor. Corresponde a un <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|
|`typeName`|Necesario para el modo `FindAncestor`. El nombre de un tipo, que rellena la propiedad <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|
|`intLevel`|Opcional para el modo `FindAncestor`. Un nivel del antecesor (se evalúa en la dirección del elemento primario en el árbol lógico).|

## <a name="remarks"></a>Observaciones

`{RelativeSource TemplatedParent}`los usos de enlace son una técnica clave que aborda un concepto más amplio de la separación de la interfaz de usuario de un control y la lógica de un control. Esto permite enlazar desde dentro de la definición de plantilla al elemento primario con plantilla (instancia de objeto en tiempo de ejecución donde se aplica la plantilla). En este caso, la extensión de [marcado TemplateBinding](templatebinding-markup-extension.md) es, `{Binding RelativeSource={RelativeSource TemplatedParent}}`de hecho, una abreviatura de la siguiente expresión de enlace: . `TemplateBinding`o `{RelativeSource TemplatedParent}` los usos solo son relevantes dentro del XAML que define una plantilla. Para obtener más información, vea [TemplateBinding Markup Extension](templatebinding-markup-extension.md).

`{RelativeSource FindAncestor}`se utiliza principalmente en plantillas de control o composiciones de interfaz de usuario independientes predecibles, para los casos en los que siempre se espera que un control esté en un árbol visual de un determinado tipo antecesor. Por ejemplo, los elementos de un control de elementos pueden usar `FindAncestor` para enlazar a propiedades del antecesor del elemento primario del control de elementos. O bien los elementos que forman parte de la composición de controles en una plantilla pueden usar enlaces `FindAncestor` a los elementos primarios en esa misma estructura de composición.

En la sintaxis de elementos de objeto para el modo `FindAncestor` que se muestra en las secciones sobre sintaxis XAML, la segunda sintaxis de elementos de objeto se emplea específicamente para el modo `FindAncestor`. El modo `FindAncestor` necesita un valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. Debe establecer <xref:System.Windows.Data.RelativeSource.AncestorType%2A> como atributo mediante una referencia [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) al tipo de antecesor que se desee buscar. Se utiliza el valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A> al procesar la solicitud de enlace en tiempo de ejecución.

Para el modo `FindAncestor`, la propiedad <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> opcional puede ayudar a eliminar la ambigüedad en la búsqueda del antecesor en aquellos casos en que sea posible que exista más de un antecesor de ese tipo en el árbol de elementos.

Para obtener más información sobre cómo usar el modo `FindAncestor`, vea <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}`es útil para escenarios donde una propiedad de una instancia debe depender del valor de otra propiedad de la misma instancia y no existe ninguna relación de propiedad de dependencia general (como la coerción) entre esas dos propiedades. Aunque es raro que existan dos propiedades en un objeto de modo que los valores sean `Converter` literalmente idénticos `{RelativeSource Self}`(y estén tipados de forma idéntica), también puede aplicar un parámetro a un enlace que tiene y usar el convertidor para convertir entre los tipos de origen y de destino. Otro escenario `{RelativeSource Self}` para es <xref:System.Windows.MultiDataTrigger>como parte de un archivo .

Por ejemplo, el código XAML siguiente define un elemento <xref:System.Windows.Shapes.Rectangle> de forma que, independientemente del valor que se especifique para <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sea siempre un cuadrado: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}`es útil en plantillas de datos o en casos en los que los enlaces usan una colección como origen de datos. Puede utilizar `{RelativeSource PreviousData}` para resaltar las relaciones entre elementos de datos adyacentes de la colección. Una técnica relacionada es establecer un objeto <xref:System.Windows.Data.MultiBinding> entre los elementos actual y anterior del origen de datos, y utilizar un convertidor en dicho enlace para determinar la diferencia entre ambos elementos y sus propiedades.

En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> de la plantilla de elementos muestra el número actual. El <xref:System.Windows.Controls.TextBlock> segundo enlace <xref:System.Windows.Data.MultiBinding> es un <xref:System.Windows.Data.Binding> que nominalmente tiene dos componentes: el registro actual `{RelativeSource PreviousData}`y un enlace que utiliza deliberadamente el registro de datos anterior mediante . A continuación, un convertidor en el objeto <xref:System.Windows.Data.MultiBinding> calcula la diferencia y la devuelve al enlace.

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

La descripción del enlace de datos como un concepto no se trata aquí, vea Información general sobre [el enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos .

En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la implementación del procesador XAML, la <xref:System.Windows.Data.RelativeSource> clase define el control de esta extensión de marcado.

`RelativeSource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones `{` de `}` marcado en XAML usan los caracteres y en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el atributo. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Data.Binding>
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre declaraciones de enlaces](../data/binding-declarations-overview.md)
- [x:Type (Extensión de marcado)](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
