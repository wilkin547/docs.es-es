---
title: Extensión de marcado RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 47117d684a981f31e22cf513fc78e1e2dda73f8a
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141260"
---
# <a name="relativesource-markupextension"></a>Extensión de marcado RelativeSource

Especifica las propiedades de <xref:System.Windows.Data.RelativeSource> un origen de enlace, que se va a utilizar dentro de una [extensión de marcado de enlace](binding-markup-extension.md)o cuando se establece la <xref:System.Windows.Data.Binding.RelativeSource%2A> propiedad de un <xref:System.Windows.Data.Binding> elemento establecido en XAML.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" ... />
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>Uso de atributos XAML (anidados en la extensión de enlace)

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" ... />
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
|`modeEnumValue`|Uno de los siguientes:<br /><br /> : El token `Self`de cadena; corresponde a un <xref:System.Windows.Data.RelativeSource> tal como se creó <xref:System.Windows.Data.RelativeSource.Mode%2A> con su propiedad <xref:System.Windows.Data.RelativeSourceMode.Self>establecida en.<br />: El token `TemplatedParent`de cadena; corresponde a un <xref:System.Windows.Data.RelativeSource> tal como se creó <xref:System.Windows.Data.RelativeSource.Mode%2A> con su propiedad <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>establecida en.<br />: El token `PreviousData`de cadena; corresponde a un <xref:System.Windows.Data.RelativeSource> tal como se creó <xref:System.Windows.Data.RelativeSource.Mode%2A> con su propiedad <xref:System.Windows.Data.RelativeSourceMode.PreviousData>establecida en.<br />-Consulte a continuación para obtener `FindAncestor` información sobre el modo.|
|`FindAncestor`|El token de cadena `FindAncestor`. Al utilizar este token, se entra en un modo en que `RelativeSource` especifica un tipo de antecesor y, opcionalmente, un nivel del antecesor. Corresponde a un <xref:System.Windows.Data.RelativeSource> creado con su propiedad <xref:System.Windows.Data.RelativeSource.Mode%2A> establecida en <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|
|`typeName`|Necesario para el modo `FindAncestor`. El nombre de un tipo, que rellena la propiedad <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|
|`intLevel`|Opcional para el modo `FindAncestor`. Un nivel del antecesor (se evalúa en la dirección del elemento primario en el árbol lógico).|

## <a name="remarks"></a>Observaciones

`{RelativeSource TemplatedParent}`los usos de enlace son una técnica clave que aborda un concepto más grande de la separación de la interfaz de usuario de un control y la lógica de un control. Esto permite enlazar desde dentro de la definición de plantilla al elemento primario con plantilla (instancia de objeto en tiempo de ejecución donde se aplica la plantilla). En este caso, la [extensión de marcado TemplateBinding](templatebinding-markup-extension.md) es en realidad una abreviatura para la siguiente expresión de `{Binding RelativeSource={RelativeSource TemplatedParent}}`enlace:. `TemplateBinding`los `{RelativeSource TemplatedParent}` usos de o solo son relevantes en el código XAML que define una plantilla. Para obtener más información, consulte [extensión de marcado TemplateBinding](templatebinding-markup-extension.md).

`{RelativeSource FindAncestor}`se usa principalmente en las plantillas de control o en las composiciones de interfaz de usuario independientes de predicción, en los casos en los que siempre se espera que un control esté en un árbol visual de un tipo de antecesor determinado. Por ejemplo, los elementos de un control de elementos pueden usar `FindAncestor` para enlazar a propiedades del antecesor del elemento primario del control de elementos. O bien los elementos que forman parte de la composición de controles en una plantilla pueden usar enlaces `FindAncestor` a los elementos primarios en esa misma estructura de composición.

En la sintaxis de elementos de objeto para el modo `FindAncestor` que se muestra en las secciones sobre sintaxis XAML, la segunda sintaxis de elementos de objeto se emplea específicamente para el modo `FindAncestor`. El modo `FindAncestor` necesita un valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. Debe establecer <xref:System.Windows.Data.RelativeSource.AncestorType%2A> como un atributo mediante una referencia de [extensión de marcado x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) al tipo de antecesor que se va a buscar. Se utiliza el valor de <xref:System.Windows.Data.RelativeSource.AncestorType%2A> al procesar la solicitud de enlace en tiempo de ejecución.

Para el modo `FindAncestor`, la propiedad <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> opcional puede ayudar a eliminar la ambigüedad en la búsqueda del antecesor en aquellos casos en que sea posible que exista más de un antecesor de ese tipo en el árbol de elementos.

Para obtener más información sobre cómo usar el modo `FindAncestor`, vea <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}`resulta útil para escenarios en los que una propiedad de una instancia debe depender del valor de otra propiedad de la misma instancia, y no existe ninguna relación de propiedad de dependencia general (como la coerción) entre esas dos propiedades. Aunque es poco frecuente que existan dos propiedades en un objeto de modo que los valores sean literalmente idénticos (y tengan tipos idénticos), también puede aplicar `Converter` un parámetro a un enlace que `{RelativeSource Self}`tenga y usar el convertidor para realizar la conversión entre los tipos de origen y de destino. Otro escenario para `{RelativeSource Self}` es como parte de un <xref:System.Windows.MultiDataTrigger>.

Por ejemplo, el código XAML siguiente define un elemento <xref:System.Windows.Shapes.Rectangle> de forma que, independientemente del valor que se especifique para <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sea siempre un cuadrado: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}`es útil en las plantillas de datos o en los casos en los que los enlaces utilizan una colección como origen de datos. Puede usar `{RelativeSource PreviousData}` para resaltar las relaciones entre los elementos de datos adyacentes de la colección. Una técnica relacionada es establecer un objeto <xref:System.Windows.Data.MultiBinding> entre los elementos actual y anterior del origen de datos, y utilizar un convertidor en dicho enlace para determinar la diferencia entre ambos elementos y sus propiedades.

En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> de la plantilla de elementos muestra el número actual. El segundo <xref:System.Windows.Controls.TextBlock> enlace es un <xref:System.Windows.Data.MultiBinding> que tiene nominalmente dos <xref:System.Windows.Data.Binding> componentes: el registro actual y un enlace que usa deliberadamente el registro de datos anterior mediante `{RelativeSource PreviousData}`. A continuación, un convertidor en el objeto <xref:System.Windows.Data.MultiBinding> calcula la diferencia y la devuelve al enlace.

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
</ListBox>
```

La descripción de los enlaces de datos como concepto no se trata aquí, vea [información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

En la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación del procesador XAML, la <xref:System.Windows.Data.RelativeSource> clase define el control para esta extensión de marcado.

`RelativeSource` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de XAML `{` usan `}` los caracteres y en su sintaxis de atributo, que es la Convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el atributo. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.Binding>
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre declaraciones de enlaces](../data/binding-declarations-overview.md)
- [x:Type (Extensión de marcado)](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
