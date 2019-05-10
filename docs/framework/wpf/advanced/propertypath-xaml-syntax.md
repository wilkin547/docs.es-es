---
title: Sintaxis de PropertyPath de XAML
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 346ce5d92fafb4d4c2c814deaa0c2b35821dc435
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611829"
---
# <a name="propertypath-xaml-syntax"></a>Sintaxis de PropertyPath de XAML
El <xref:System.Windows.PropertyPath> objeto admite una insertada compleja [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis para establecer varias propiedades que toman el <xref:System.Windows.PropertyPath> tipo como su valor. Este tema se documenta el <xref:System.Windows.PropertyPath> sintaxis que se aplican a la sintaxis de enlace y animación.  

<a name="where"></a>   
## <a name="where-propertypath-is-used"></a>Dónde se usa PropertyPath  
 <xref:System.Windows.PropertyPath> es un objeto común que se utiliza en varios [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] características. A pesar de usar común <xref:System.Windows.PropertyPath> para transmitir información de ruta de acceso de propiedad, los usos de cada área de características donde <xref:System.Windows.PropertyPath> se usa como un tipo varían. Por lo tanto, es más práctico documentar las sintaxis por característica.  
  
 Principalmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa <xref:System.Windows.PropertyPath> para describir las rutas de acceso del modelo de objetos para recorrer las propiedades de un origen de datos de objeto y para describir la ruta de acceso de destino para animaciones concretas.  
  
 Algunas propiedades de estilo y plantilla como <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> toman un nombre de propiedad completo que se parezca ligeramente a un <xref:System.Windows.PropertyPath>. Pero esto no es un verdadero <xref:System.Windows.PropertyPath>; en su lugar, es un completo *owner.property* cadena el uso de formato que está habilitado de forma WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador en combinación con el convertidor de tipos para <xref:System.Windows.DependencyProperty>.  
  
<a name="databinding_s"></a>   
## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath para objetos al enlazar datos  
 El enlace de datos es una característica de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que permite enlazar con el valor de destino de cualquier propiedad de dependencia. Sin embargo, el origen de este tipo de enlace de datos no necesita ser una propiedad de dependencia: puede ser cualquier tipo de propiedad que reconozca el proveedor de datos correspondiente. Las rutas de acceso de propiedad se usan especialmente para la <xref:System.Windows.Data.ObjectDataProvider>, que se usa para obtener los orígenes de enlace de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objetos y sus propiedades.  
  
 Tenga en cuenta que el enlace de datos a [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] no usa <xref:System.Windows.PropertyPath>, ya que no utiliza <xref:System.Windows.Data.Binding.Path%2A> en el <xref:System.Windows.Data.Binding>. En su lugar, usa <xref:System.Windows.Data.Binding.XPath%2A> y especifique la sintaxis de XPath válida en el [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] de los datos. <xref:System.Windows.Data.Binding.XPath%2A> También se especifica como una cadena, pero no se documenta aquí: consulte [enlazar a datos XML mediante XMLDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Una clave para entender las rutas de acceso de propiedad de enlace de datos es que puede tener como destino el enlace a un valor de propiedad individual o, en su lugar, puede enlazar a propiedades de destino que acepten listas o colecciones. Si va a enlazar colecciones, por ejemplo enlace un <xref:System.Windows.Controls.ListBox> que se expandirá en función de cuántos elementos de datos están en la colección y, después, la ruta de acceso de propiedad debe hacer referencia el objeto de colección, elementos de colección no individuales. El motor de enlace de datos coincidirá con la colección utilizada como origen de datos para el tipo del destino de enlace automáticamente, lo que resulta en un comportamiento como rellenar un <xref:System.Windows.Controls.ListBox> con una matriz de elementos.  
  
<a name="singlecurrent"></a>   
### <a name="single-property-on-the-immediate-object-as-data-context"></a>Propiedad única en el objeto inmediato como contexto de datos  
  
```xml  
<Binding Path="propertyName" .../>  
```  
  
 *propertyName* debe resolverse para ser el nombre de una propiedad que se encuentra en la actual <xref:System.Windows.FrameworkElement.DataContext%2A> para un <xref:System.Windows.Data.Binding.Path%2A> uso. Si el enlace actualiza el origen, esa propiedad debe ser de lectura y escritura, y el objeto de destino debe ser mutable.  
  
<a name="singleindex"></a>   
### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Indizador único en el objeto inmediato como contexto de datos  
  
```xml  
<Binding Path="[key]" .../>  
```  
  
 `key` debe ser el índice con tipo de un diccionario o una tabla hash, o el índice de entero de una matriz. Además, el valor de la clave debe ser un tipo que se pueda enlazar directamente a la propiedad donde se aplica. Por ejemplo, una tabla hash que contiene las claves de cadena y valores de cadena puede utilizarse de este modo para enlazar al texto para un <xref:System.Windows.Controls.TextBox>. O bien, si la clave apunta a una colección o un subíndice, puede usar esta sintaxis para enlazar a una propiedad de colección de destino. De lo contrario, deberá hacer referencia a una propiedad específica, mediante una sintaxis como `<Binding Path="[key].propertyName" .../>`.  
  
 Puede especificar el tipo del índice, si es necesario. Para obtener más información sobre este aspecto de una ruta de acceso de propiedad indizada, vea <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.  
  
<a name="multipleindirect"></a>   
### <a name="multiple-property-indirect-property-targeting"></a>Varias propiedades (destino de propiedad indirecto)  
  
```xml  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName` debe resolverse para ser el nombre de una propiedad que es el actual <xref:System.Windows.FrameworkElement.DataContext%2A>. Las propiedades de ruta de acceso `propertyName` y `propertyName2` pueden ser cualquier propiedad que exista en una relación, donde `propertyName2` es una propiedad que existe en el tipo que es el valor de `propertyName`.  
  
<a name="singleattached"></a>   
### <a name="single-property-attached-or-otherwise-type-qualified"></a>Propiedad única, adjunta o calificada por tipo  
  
```xml  
<object property="(ownerType.propertyName)" .../>  
```  
  
 Los paréntesis indican que esta propiedad en un <xref:System.Windows.PropertyPath> deben crearse con una calificación parcial. Puede usar un espacio de nombres XML para buscar el tipo con la asignación adecuada. El `ownerType` busca tipos a los que un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador tenga acceso a través del <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declaraciones en cada ensamblado. La mayoría de las aplicaciones tienen el espacio de nombres XML predeterminado asignado al espacio de nombres [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], de modo que, normalmente, solo es necesario para los tipos personalizados o para tipos que queden fuera del espacio de nombres.  `propertyName` debe resolverse para ser el nombre de una propiedad que exista en `ownerType`. Esta sintaxis se usa, normalmente, para uno de los siguientes casos:  
  
- Se especifica la ruta de acceso en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que tiene un estilo o plantilla sin un tipo de destino especificado. Un uso completo, normalmente, no es válido para otros casos que no sean este, porque en los casos sin estilo o sin plantilla, la propiedad existe en una instancia, no en un tipo.  
  
- La propiedad es una propiedad adjunta.  
  
- Está enlazando a una propiedad estática.  
  
 Para usar como destino de guión gráfico, la propiedad especificada como `propertyName` debe ser un <xref:System.Windows.DependencyProperty>.  
  
<a name="sourcetraversal"></a>   
### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Recorrido de origen (enlace a jerarquías de colecciones)  
  
```xml  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 El carácter / de esta sintaxis se usa para navegar dentro de un objeto de origen de datos jerárquicos y se admiten varios pasos en la jerarquía con caracteres / sucesivos. El recorrido de origen representa la posición del puntero de registro actual, que se determina mediante la sincronización de los datos con la interfaz de usuario de su vista. Para obtener más información sobre el enlace con objetos de origen de datos jerárquicos y el concepto de puntero de registro actual en el enlace de datos, consulte [Usar el patrón principal-detalle con datos jerárquicos](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) o [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
> [!NOTE]
>  Esta sintaxis se parece ligeramente a [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Un verdadero [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] expresión para el enlace a un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] origen de datos no se utiliza como un <xref:System.Windows.Data.Binding.Path%2A> de valor y en su lugar debe usarse para mutuamente excluyentes <xref:System.Windows.Data.Binding.XPath%2A> propiedad.  
  
### <a name="collection-views"></a>Vistas de colección  
 Para hacer referencia a una vista de colección con nombre, use el carácter almohadilla (`#`) como prefijo del nombre de vista de colección.  
  
### <a name="current-record-pointer"></a>Puntero de registro actual  
 Para hacer referencia al puntero de registro actual de un escenario de vista de colección o enlace de datos principal-detalle, inicie la cadena de ruta de acceso con una barra diagonal (`/`). Cualquier ruta de acceso posterior a la barra diagonal se recorre desde el puntero de registro actual.  
  
### <a name="multiple-indexers"></a>Varios indizadores  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 Si un objeto determinado admite varios indizadores, estos pueden especificarse en orden, de un modo similar a una matriz que hace referencia a la sintaxis. El objeto en cuestión puede ser el contexto actual o el valor de una propiedad que contenga un objeto de índice múltiple.  
  
 De forma predeterminada, se asignan tipos a los valores del indizador con las características del objeto subyacente. Puede especificar el tipo del índice, si es necesario. Para obtener más información sobre tipos a los indizadores, vea <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.  
  
<a name="mixing"></a>   
### <a name="mixing-syntaxes"></a>Sintaxis mixtas  
 Se pueden intercalar todas las sintaxis mostradas anteriormente. Por ejemplo, el siguiente es un ejemplo que crea una ruta de acceso de propiedad para el color en una x, y determinada de un `ColorGrid` propiedad que contiene una matriz de cuadrícula de píxeles <xref:System.Windows.Media.SolidColorBrush> objetos:  
  
```xml  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### <a name="escapes-for-property-path-strings"></a>Secuencias de escape para cadenas de ruta de acceso de propiedad  
 Para ciertos objetos de negocios, puede encontrar un caso donde la cadena de ruta de acceso de propiedad necesite una secuencia de escape para poder analizarse correctamente. La necesidad de la secuencia de escape no es habitual, ya que muchos de estos caracteres tienen problemas similares de interacción con nombres en lenguajes que, normalmente, se usarían para definir el objeto de negocios.  
  
- Dentro de los indizadores ([ ]), el carácter de intercalación (^) realiza el escape del carácter siguiente.  
  
- Debe realizar el escape (mediante entidades XML) de determinados caracteres que son especiales para la definición del lenguaje XML. Use `&` para realizar el escape del carácter "&". Use `>` para realizar el escape de la etiqueta final ">".  
  
- Debe realizar el escape (con la barra diagonal inversa `\`) de caracteres que son especiales para el comportamiento del analizador XAML de WPF para procesar una extensión de marcado.  
  
    - La barra diagonal inversa (`\`) es el carácter de escape.  
  
    - El signo igual (`=`) separa el nombre de propiedad del valor de propiedad.  
  
    - La coma (`,`) separa las propiedades.  
  
    - La llave de cierre (`}`) es el final de una extensión de marcado.  
  
> [!NOTE]
>  Técnicamente, estos escapes también funcionan para una ruta de acceso de propiedad de guion gráfico, pero, normalmente, se recorren modelos de objetos para los objetos WPF existentes y las secuencias de escape no deberían ser necesarias.  
  
<a name="databinding_sa"></a>   
## <a name="propertypath-for-animation-targets"></a>PropertyPath para destinos de animación  
 La propiedad de destino de una animación debe ser una propiedad de dependencia que acepta un <xref:System.Windows.Freezable> o un tipo primitivo. Sin embargo, la propiedad de destino de un tipo y la propiedad animada final pueden existir en objetos diferentes. Para las animaciones, se usa una ruta de acceso de propiedad para definir la conexión entre la propiedad del objeto de destino de animación con nombre y la propiedad de animación de destino prevista, si se recorren las relaciones de propiedad del objeto en los valores de propiedad.  
  
<a name="general"></a>   
### <a name="general-object-property-considerations-for-animations"></a>Consideraciones de las propiedades de objetos generales para animaciones  
 Para obtener más información sobre los conceptos de animación en general, consulte [Información general sobre objetos Storyboard](../graphics-multimedia/storyboards-overview.md) e [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
 El tipo de valor o la propiedad que se anima debe ser un <xref:System.Windows.Freezable> o un tipo primitivo. La propiedad que inicia la ruta de acceso debe resolverse para ser el nombre de una propiedad de dependencia que existe en el objeto <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> tipo.  
  
 Con el fin de admitir la clonación para animar un <xref:System.Windows.Freezable> ya está inmovilizado, el objeto especificado por <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> debe ser un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> clase derivada.  
  
<a name="singlestepanim"></a>   
### <a name="single-property-on-the-target-object"></a>Propiedad única en el objeto de destino  
  
```xml  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName` debe resolverse para ser el nombre de una propiedad de dependencia que existe en el objeto <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> tipo.  
  
<a name="indirectanim"></a>   
### <a name="indirect-property-targeting"></a>Destino de propiedad indirecto  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName` debe ser una propiedad que sea un <xref:System.Windows.Freezable> valor o un tipo primitivo, que existe en el objeto <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> tipo.  
  
 `propertyName2` debe ser el nombre de una propiedad de dependencia que exista en el objeto que es el valor de `propertyName`. En otras palabras, `propertyName2` debe existir como una propiedad de dependencia en el tipo que es el `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.  
  
 El destino indirecto de animaciones es necesario debido a los estilos y las plantillas que se aplican. Para tener como destino una animación, necesita un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> en un objeto de destino y de que el nombre se establece mediante la [x: Name](../../xaml-services/x-name-directive.md) o <xref:System.Windows.FrameworkElement.Name%2A>. Aunque los elementos de plantilla y estilo también pueden tener nombres, esos nombres solo son válidos en el ámbito de nombres de la plantilla y el estilo. (Si las plantillas y los estilos compartieran ámbitos de nombres con el marcado de la aplicación, los nombres no podrían ser únicos. Los estilos y las plantillas se comparten literalmente entre instancias y se perpetuarían los nombres duplicados). Por lo tanto, si las propiedades individuales de un elemento que quiere animar proceden de un estilo o una plantilla, debe comenzar con una instancia de elemento con nombre que no sea de una plantilla de estilo y, a continuación, dirigirse al árbol visual de estilos o plantillas para llegar a la propiedad que quiere animar.  
  
 Por ejemplo, el <xref:System.Windows.Controls.Panel.Background%2A> propiedad de un <xref:System.Windows.Controls.Panel> es una completa <xref:System.Windows.Media.Brush> (realmente un <xref:System.Windows.Media.SolidColorBrush>) que proviene de una plantilla de tema. Para animar un <xref:System.Windows.Media.Brush> completamente, debería haber un tipo BrushAnimation (probablemente, uno por cada <xref:System.Windows.Media.Brush> tipo) y no hay ningún tipo de este tipo. Para animar un pincel, en su lugar, anima las propiedades de una determinada <xref:System.Windows.Media.Brush> tipo. Deberá obtener desde <xref:System.Windows.Media.SolidColorBrush> a su <xref:System.Windows.Media.SolidColorBrush.Color%2A> para aplicar un <xref:System.Windows.Media.Animation.ColorAnimation> no existe. La ruta de acceso de propiedad de este ejemplo sería `Background.Color`.  
  
<a name="attachedanim"></a>   
### <a name="attached-properties"></a>Propiedades asociadas  
  
```xml  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 Los paréntesis indican que esta propiedad en un <xref:System.Windows.PropertyPath> deben crearse con una calificación parcial. Puede usar un espacio de nombres XML para buscar el tipo. El `ownerType` busca tipos a los que un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador tenga acceso a través del <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declaraciones en cada ensamblado. La mayoría de las aplicaciones tienen el espacio de nombres XML predeterminado asignado al espacio de nombres [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], de modo que, normalmente, solo es necesario para los tipos personalizados o para tipos que queden fuera del espacio de nombres. `propertyName` debe resolverse para ser el nombre de una propiedad que exista en `ownerType`. La propiedad especificada como `propertyName` debe ser un <xref:System.Windows.DependencyProperty>. (Todas las propiedades adjuntas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementan como propiedades de dependencia, por lo que este problema solo afecta a las propiedades adjuntas personalizadas).  
  
<a name="indexanim"></a>   
### <a name="indexers"></a>Indizadores  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 La mayoría de las propiedades de dependencia o <xref:System.Windows.Freezable> tipos no admiten un indizador. Por lo tanto, el único uso de un indizador en una ruta de acceso de animación está en una posición intermedia entre la propiedad que inicia la cadena en el destino con nombre y la propiedad animada final. En la sintaxis proporcionada, es `propertyName2`. Por ejemplo, el uso del indizador podría ser necesario si la propiedad intermedia es una colección, como <xref:System.Windows.Media.TransformGroup>, en una ruta de acceso de propiedad como `RenderTransform.Children[1].Angle`.  
  
<a name="ppincode"></a>   
## <a name="propertypath-in-code"></a>PropertyPath en código  
 Código de uso para <xref:System.Windows.PropertyPath>, incluida la forma de construir un <xref:System.Windows.PropertyPath>, se documenta en el tema de referencia <xref:System.Windows.PropertyPath>.  
  
 En general, <xref:System.Windows.PropertyPath> está diseñado para usar dos constructores diferentes, uno para los usos de enlace y los usos de animación más simple y otro para los usos de animación complejos. Use el <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> firma para usos de enlace, donde el objeto es una cadena. Use la <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> firma para rutas de acceso de animación de un solo paso, donde el objeto es un <xref:System.Windows.DependencyProperty>. Use el <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> para animaciones complejas. Este último constructor usa una cadena de token para el primer parámetro y una matriz de objetos que rellenan las posiciones en la cadena de token para definir una relación de ruta de acceso de propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.PropertyPath>
- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Información general sobre objetos Storyboard ](../graphics-multimedia/storyboards-overview.md)
