---
title: Sintaxis de PropertyPath de XAML
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 817ce750cdad58e504eef5144cfb8a2813bca596
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141291"
---
# <a name="propertypath-xaml-syntax"></a>Sintaxis de PropertyPath de XAML

El <xref:System.Windows.PropertyPath> objeto admite una sintaxis insertada [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compleja para establecer varias propiedades que toman el <xref:System.Windows.PropertyPath> tipo como su valor. En este tema se <xref:System.Windows.PropertyPath> documenta la sintaxis que se aplica a las sintaxis de enlace y animación.

<a name="where"></a>

## <a name="where-propertypath-is-used"></a>Dónde se usa PropertyPath

<xref:System.Windows.PropertyPath>es un objeto común que se usa en varias [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] características. A pesar de usar Common <xref:System.Windows.PropertyPath> para transmitir información de la ruta de acceso de la propiedad, los usos <xref:System.Windows.PropertyPath> de cada área de características donde se usa como tipo varían. Por lo tanto, es más práctico documentar las sintaxis por característica.

Principalmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa <xref:System.Windows.PropertyPath> para describir las rutas de acceso del modelo de objetos para atravesar las propiedades de un origen de datos de objeto y para describir la ruta de acceso de destino para las animaciones de destino.

Algunas propiedades de estilo y plantilla, <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> como toman un nombre de propiedad completo que se parece superficialmente a <xref:System.Windows.PropertyPath>. Pero esto no es cierto <xref:System.Windows.PropertyPath>. en su lugar, es un *propietario calificado.* uso del formato de cadena de propiedad que está [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] habilitado por el procesador de WPF en <xref:System.Windows.DependencyProperty>combinación con el convertidor de tipos de.

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath para objetos al enlazar datos

El enlace de datos es una característica de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que permite enlazar con el valor de destino de cualquier propiedad de dependencia. Sin embargo, el origen de este tipo de enlace de datos no necesita ser una propiedad de dependencia: puede ser cualquier tipo de propiedad que reconozca el proveedor de datos correspondiente. Las rutas de acceso de propiedad se <xref:System.Windows.Data.ObjectDataProvider>utilizan especialmente para, que se usa para obtener los orígenes de enlace de los objetos Common Language Runtime (CLR) y sus propiedades.

Tenga en cuenta que el enlace de datos a <xref:System.Windows.PropertyPath>XML no utiliza, porque no <xref:System.Windows.Data.Binding.Path%2A> utiliza en <xref:System.Windows.Data.Binding>. En su lugar, use <xref:System.Windows.Data.Binding.XPath%2A> y especifique la sintaxis de XPath válida en el Document Object Model XML (dom) de los datos. <xref:System.Windows.Data.Binding.XPath%2A>también se especifica como una cadena, pero no se documenta aquí. vea [enlazar a datos XML mediante XmlDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).

Una clave para entender las rutas de acceso de propiedad de enlace de datos es que puede tener como destino el enlace a un valor de propiedad individual o, en su lugar, puede enlazar a propiedades de destino que acepten listas o colecciones. Si va a enlazar colecciones, para el enlace <xref:System.Windows.Controls.ListBox> de instancias que se expandirá en función del número de elementos de datos que haya en la colección, la ruta de acceso de la propiedad debe hacer referencia al objeto de colección, no a elementos individuales de la colección. El motor de enlace de datos hará coincidir automáticamente la colección utilizada como origen de datos con el tipo del destino de enlace, lo que dará lugar <xref:System.Windows.Controls.ListBox> a un comportamiento como el rellenado de un elemento con una matriz de elementos.

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a>Propiedad única en el objeto inmediato como contexto de datos

```xml
<Binding Path="propertyName" ... />
```

*PropertyName* debe resolverse como el nombre de una propiedad que está en el actual <xref:System.Windows.FrameworkElement.DataContext%2A> para un <xref:System.Windows.Data.Binding.Path%2A> uso. Si el enlace actualiza el origen, esa propiedad debe ser de lectura y escritura, y el objeto de destino debe ser mutable.

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Indizador único en el objeto inmediato como contexto de datos

```xml
<Binding Path="[key]" ... />
```

`key` debe ser el índice con tipo de un diccionario o una tabla hash, o el índice de entero de una matriz. Además, el valor de la clave debe ser un tipo que se pueda enlazar directamente a la propiedad donde se aplica. Por ejemplo, una tabla hash que contiene claves de cadena y valores de cadena se puede usar de esta manera para enlazar <xref:System.Windows.Controls.TextBox>al texto de un. O bien, si la clave apunta a una colección o un subíndice, puede usar esta sintaxis para enlazar a una propiedad de colección de destino. De lo contrario, deberá hacer referencia a una propiedad específica, mediante una sintaxis como `<Binding Path="[key].propertyName" .../>`.

Puede especificar el tipo del índice si es necesario. Para obtener más información sobre este aspecto de una ruta de acceso <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>de propiedad indizada, vea.

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a>Varias propiedades (destino de propiedad indirecto)

```xml
<Binding Path="propertyName.propertyName2" ... />
```

`propertyName`debe resolverse para ser el nombre de una propiedad que sea el <xref:System.Windows.FrameworkElement.DataContext%2A>actual. Las propiedades de ruta de acceso `propertyName` y `propertyName2` pueden ser cualquier propiedad que exista en una relación, donde `propertyName2` es una propiedad que existe en el tipo que es el valor de `propertyName`.

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a>Propiedad única, adjunta o calificada por tipo

```xml
<object property="(ownerType.propertyName)" ... />
```

Los paréntesis indican que esta propiedad de se <xref:System.Windows.PropertyPath> debe construir usando una calificación parcial. Puede usar un espacio de nombres XML para buscar el tipo con la asignación adecuada. `ownerType` Busca en los tipos a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] los que un procesador tiene acceso, <xref:System.Windows.Markup.XmlnsDefinitionAttribute> a través de las declaraciones de cada ensamblado. La mayoría de las aplicaciones tienen el espacio de nombres XML predeterminado asignado al espacio de nombres `http://schemas.microsoft.com/winfx/2006/xaml/presentation`, de modo que, normalmente, solo es necesario para los tipos personalizados o para tipos que queden fuera del espacio de nombres.  `propertyName` debe resolverse para ser el nombre de una propiedad que exista en `ownerType`. Esta sintaxis se usa, normalmente, para uno de los siguientes casos:

- Se especifica la ruta de acceso en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que tiene un estilo o plantilla sin un tipo de destino especificado. Un uso completo, normalmente, no es válido para otros casos que no sean este, porque en los casos sin estilo o sin plantilla, la propiedad existe en una instancia, no en un tipo.

- La propiedad es una propiedad adjunta.

- Está enlazando a una propiedad estática.

Para usar como destino de guion gráfico, la propiedad `propertyName` especificada como debe <xref:System.Windows.DependencyProperty>ser.

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Recorrido de origen (enlace a jerarquías de colecciones)

```xml
<object Path="propertyName/propertyNameX" ... />
```

El carácter / de esta sintaxis se usa para navegar dentro de un objeto de origen de datos jerárquicos y se admiten varios pasos en la jerarquía con caracteres / sucesivos. El recorrido de origen representa la posición del puntero de registro actual, que se determina mediante la sincronización de los datos con la interfaz de usuario de su vista. Para obtener más información sobre el enlace con objetos de origen de datos jerárquicos y el concepto de puntero de registro actual en el enlace de datos, consulte [Usar el patrón principal-detalle con datos jerárquicos](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) o [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).

> [!NOTE]
> Superficialmente, esta sintaxis es similar a XPath. Una expresión XPath verdadera para el enlace a un origen de datos XML no se utiliza <xref:System.Windows.Data.Binding.Path%2A> como valor y, en su lugar, se debe usar para <xref:System.Windows.Data.Binding.XPath%2A> la propiedad mutuamente excluyente.

### <a name="collection-views"></a>Vistas de colección

Para hacer referencia a una vista de colección con nombre, use el carácter almohadilla (`#`) como prefijo del nombre de vista de colección.

### <a name="current-record-pointer"></a>Puntero de registro actual

Para hacer referencia al puntero de registro actual de un escenario de vista de colección o enlace de datos principal-detalle, inicie la cadena de ruta de acceso con una barra diagonal (`/`). Cualquier ruta de acceso posterior a la barra diagonal se recorre desde el puntero de registro actual.

### <a name="multiple-indexers"></a>Varios indizadores

```xaml
<object Path="[index1,index2...]" ... />
```

o

```xaml
<object Path="propertyName[index,index2...]" ... />
```

Si un objeto determinado admite varios indizadores, estos pueden especificarse en orden, de un modo similar a una matriz que hace referencia a la sintaxis. El objeto en cuestión puede ser el contexto actual o el valor de una propiedad que contenga un objeto de índice múltiple.

De forma predeterminada, se asignan tipos a los valores del indizador con las características del objeto subyacente. Puede especificar el tipo del índice si es necesario. Para obtener información detallada sobre cómo escribir los indizadores, vea <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a>Sintaxis mixtas

Se pueden intercalar todas las sintaxis mostradas anteriormente. Por ejemplo, a continuación se muestra un ejemplo que crea una ruta de acceso de propiedad al color en una x, y `ColorGrid` determinada de una propiedad que contiene una matriz <xref:System.Windows.Media.SolidColorBrush> de objetos de cuadrícula de píxeles:

```xml
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" ... />
```

### <a name="escapes-for-property-path-strings"></a>Secuencias de escape para cadenas de ruta de acceso de propiedad

Para ciertos objetos de negocios, puede encontrar un caso donde la cadena de ruta de acceso de propiedad necesite una secuencia de escape para poder analizarse correctamente. La necesidad de la secuencia de escape no es habitual, ya que muchos de estos caracteres tienen problemas similares de interacción con nombres en lenguajes que, normalmente, se usarían para definir el objeto de negocios.

- Dentro de los indizadores ([ ]), el carácter de intercalación (^) realiza el escape del carácter siguiente.

- Debe realizar el escape (mediante entidades XML) de determinados caracteres que son especiales para la definición del lenguaje XML. Use `&` para realizar el escape del carácter "&". Use `>` para realizar el escape de la etiqueta final ">".

- Debe realizar el escape (con la barra diagonal inversa `\`) de caracteres que son especiales para el comportamiento del analizador XAML de WPF para procesar una extensión de marcado.

  - La barra diagonal inversa (`\`) es el mismo carácter de escape.

  - El signo igual (`=`) separa el nombre de propiedad del valor de propiedad.

  - La coma (`,`) separa las propiedades.

  - La llave de cierre (`}`) es el final de una extensión de marcado.

> [!NOTE]
> Técnicamente, estos escapes también funcionan para una ruta de acceso de propiedad de guion gráfico, pero, normalmente, se recorren modelos de objetos para los objetos WPF existentes y las secuencias de escape no deberían ser necesarias.

<a name="databinding_sa"></a>

## <a name="propertypath-for-animation-targets"></a>PropertyPath para destinos de animación

La propiedad de destino de una animación debe ser una propiedad de dependencia que toma <xref:System.Windows.Freezable> o un tipo primitivo. Sin embargo, la propiedad de destino de un tipo y la propiedad animada final pueden existir en objetos diferentes. Para las animaciones, se usa una ruta de acceso de propiedad para definir la conexión entre la propiedad del objeto de destino de animación con nombre y la propiedad de animación de destino prevista, si se recorren las relaciones de propiedad del objeto en los valores de propiedad.

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a>Consideraciones de las propiedades de objetos generales para animaciones

Para obtener más información sobre los conceptos de animación en general, consulte [Información general sobre objetos Storyboard](../graphics-multimedia/storyboards-overview.md) e [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).

El tipo de valor o la propiedad que se está animando <xref:System.Windows.Freezable> debe ser un tipo o un primitivo. La propiedad que inicia la ruta de acceso debe resolverse como el nombre de una propiedad de dependencia que existe <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> en el tipo especificado.

Con el fin de admitir la clonación para <xref:System.Windows.Freezable> animar un que ya está inmovilizado <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> , el objeto <xref:System.Windows.FrameworkElement> especificado <xref:System.Windows.FrameworkContentElement> por debe ser una clase derivada o.

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a>Propiedad única en el objeto de destino

```xml
<animation Storyboard.TargetProperty="propertyName" ... />
```

`propertyName`debe resolverse para ser el nombre de una propiedad de dependencia que exista en <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> el tipo especificado.

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a>Destino de propiedad indirecto

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" ... />
```

`propertyName`debe ser una propiedad que sea un <xref:System.Windows.Freezable> tipo de valor o un primitivo, que existe en el tipo <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> especificado.

`propertyName2` debe ser el nombre de una propiedad de dependencia que exista en el objeto que es el valor de `propertyName`. En otras palabras, `propertyName2` debe existir como una propiedad de dependencia en el tipo que es `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.

El destino indirecto de animaciones es necesario debido a los estilos y las plantillas que se aplican. Para dirigirse a una animación, necesita un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> en un objeto de destino y ese nombre se establece mediante [x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) o. <xref:System.Windows.FrameworkElement.Name%2A> Aunque los elementos de plantilla y estilo también pueden tener nombres, esos nombres solo son válidos en el ámbito de nombres de la plantilla y el estilo. (Si las plantillas y los estilos compartieran ámbitos de nombres con el marcado de la aplicación, los nombres no podrían ser únicos. Los estilos y las plantillas se comparten literalmente entre instancias y perpetuarían nombres duplicados.) Por lo tanto, si las propiedades individuales de un elemento que desea animar provienen de un estilo o una plantilla, debe comenzar con una instancia de elemento con nombre que no sea de una plantilla de estilo y, a continuación, destinarla al árbol visual de estilo o plantilla para llegar a la propiedad que desea animar.

Por ejemplo, la <xref:System.Windows.Controls.Panel.Background%2A> propiedad de un <xref:System.Windows.Controls.Panel> es un completo <xref:System.Windows.Media.Brush> (realmente un <xref:System.Windows.Media.SolidColorBrush>) procedente de una plantilla de tema. Para animar <xref:System.Windows.Media.Brush> un por completo, debería haber un BrushAnimation (probablemente uno para cada <xref:System.Windows.Media.Brush> tipo) y no existe ese tipo. Para animar un pincel, en lugar de animar las propiedades <xref:System.Windows.Media.Brush> de un tipo determinado. Debe obtener de <xref:System.Windows.Media.SolidColorBrush> a su <xref:System.Windows.Media.SolidColorBrush.Color%2A> para aplicar <xref:System.Windows.Media.Animation.ColorAnimation> allí. La ruta de acceso de propiedad de este ejemplo sería `Background.Color`.

<a name="attachedanim"></a>

### <a name="attached-properties"></a>Propiedades asociadas

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" ... />
```

Los paréntesis indican que esta propiedad de se <xref:System.Windows.PropertyPath> debe construir usando una calificación parcial. Puede usar un espacio de nombres XML para buscar el tipo. `ownerType` Busca en los tipos a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] los que un procesador tiene acceso, <xref:System.Windows.Markup.XmlnsDefinitionAttribute> a través de las declaraciones de cada ensamblado. La mayoría de las aplicaciones tienen el espacio de nombres XML predeterminado asignado al espacio de nombres `http://schemas.microsoft.com/winfx/2006/xaml/presentation`, de modo que, normalmente, solo es necesario para los tipos personalizados o para tipos que queden fuera del espacio de nombres. `propertyName` debe resolverse para ser el nombre de una propiedad que exista en `ownerType`. La propiedad especificada como `propertyName` debe ser <xref:System.Windows.DependencyProperty>. (Todas las propiedades adjuntas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementan como propiedades de dependencia, por lo que este problema solo afecta a las propiedades adjuntas personalizadas).

<a name="indexanim"></a>

### <a name="indexers"></a>Indexadores

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" ... />
```

La mayoría de los <xref:System.Windows.Freezable> tipos o propiedades de dependencia no admiten un indexador. Por lo tanto, el único uso de un indizador en una ruta de acceso de animación está en una posición intermedia entre la propiedad que inicia la cadena en el destino con nombre y la propiedad animada final. En la sintaxis proporcionada, es `propertyName2`. Por ejemplo, un uso del indexador podría ser necesario si la propiedad intermedia es una colección como <xref:System.Windows.Media.TransformGroup>, en una ruta de acceso de `RenderTransform.Children[1].Angle`propiedad como.

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a>PropertyPath en código

El uso del <xref:System.Windows.PropertyPath>código para, incluido cómo construir <xref:System.Windows.PropertyPath>un, se documenta en el tema de <xref:System.Windows.PropertyPath>referencia para.

En general, <xref:System.Windows.PropertyPath> está diseñado para usar dos constructores diferentes, uno para los usos de enlace y los usos de animación más sencillos, y otro para los usos de animación complejos. Use la <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> firma para los usos de enlace, donde el objeto es una cadena. Use la <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> firma para las rutas de acceso de animación de un paso, donde <xref:System.Windows.DependencyProperty>el objeto es. Use la <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> firma para animaciones complejas. Este último constructor usa una cadena de token para el primer parámetro y una matriz de objetos que rellenan las posiciones en la cadena de token para definir una relación de ruta de acceso de propiedad.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.PropertyPath>
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre objetos Storyboard](../graphics-multimedia/storyboards-overview.md)
