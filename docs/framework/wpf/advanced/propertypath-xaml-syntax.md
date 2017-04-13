---
title: "Sintaxis de PropertyPath de XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PropertyPath (objeto)"
  - "XAML, PropertyPath (objeto)"
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Sintaxis de PropertyPath de XAML
El objeto <xref:System.Windows.PropertyPath> admite una sintaxis insertada [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compleja para establecer varias propiedades que toman el tipo <xref:System.Windows.PropertyPath> como valor.  En este tema se documenta la sintaxis de <xref:System.Windows.PropertyPath> tal como se aplica a las sintaxis de enlace y animación.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="where"></a>   
## Donde se utiliza PropertyPath  
 <xref:System.Windows.PropertyPath> es un objeto común que se utiliza en varias características de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Aunque se utilice el objeto común <xref:System.Windows.PropertyPath> para llevar información de la ruta de acceso de propiedad, los usos para cada área de características donde se utiliza <xref:System.Windows.PropertyPath> como un tipo varían.  Por consiguiente, es más práctico documentar las sintaxis característica por característica.  
  
 Principalmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza <xref:System.Windows.PropertyPath> para describir rutas de acceso del modelo de objetos para recorrer las propiedades de un origen de datos de objeto y para describir rutas de acceso de destino para animaciones concretas.  
  
 Algunas propiedades de estilo y de plantilla, tales como <xref:System.Windows.Setter.Property%2A?displayProperty=fullName>, aceptan un nombre de propiedad completo similar, superficialmente, a un objeto <xref:System.Windows.PropertyPath>.  No obstante, no es un verdadero objeto <xref:System.Windows.PropertyPath>, sino que se trata de un uso con el formato de cadena calificada con *propietario.propiedad*, habilitado por el procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de WPF en combinación con el convertidor de tipos para <xref:System.Windows.DependencyProperty>.  
  
<a name="databinding_s"></a>   
## PropertyPath para objetos de enlace de datos  
 El enlace de datos es una característica de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que permite enlazar al valor de destino de cualquier [propiedad de dependencia](GTMT).  Sin embargo, no es necesario que el origen de tal enlace de datos sea una [propiedad de dependencia](GTMT); puede ser cualquier tipo de propiedad que reconozca el proveedor de datos correspondiente.  Las rutas de acceso de las propiedades se usan especialmente para la clase <xref:System.Windows.Data.ObjectDataProvider>, que se utiliza para obtener los orígenes de enlace de objetos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y sus propiedades.  
  
 Observe que el enlace de datos a [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] no utiliza <xref:System.Windows.PropertyPath>, porque no utiliza <xref:System.Windows.Data.Binding.Path%2A> en <xref:System.Windows.Data.Binding>.  En su lugar, use <xref:System.Windows.Data.Binding.XPath%2A> y especifique una sintaxis XPath válida en el [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] de los datos.  <xref:System.Windows.Data.Binding.XPath%2A> también se especifica como una cadena, pero no se documenta aquí; vea [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Una clave para entender las rutas de acceso de propiedad en el enlace de datos es que es posible destinar el enlace a un valor de propiedad individual o, en su lugar, enlazar a propiedades de destino que acepten listas o colecciones.  Si va a enlazar colecciones, por ejemplo un control <xref:System.Windows.Controls.ListBox> que se expandirá en función de cuántos elementos de datos haya en la colección, la ruta de acceso de la propiedad debería hacer referencia al objeto de colección, no a los elementos de colección individuales.  El motor de enlace de datos relacionará la colección utilizada automáticamente como origen de datos con el destino del enlace; el comportamiento resultante será el rellenado de un control <xref:System.Windows.Controls.ListBox> con una matriz de elementos.  
  
<a name="singlecurrent"></a>   
### Propiedad única en el objeto inmediato como contexto de datos  
  
```  
<Binding Path="propertyName" .../>  
```  
  
 *propertyName* debe resolverse en el nombre de una propiedad que esté en el <xref:System.Windows.FrameworkElement.DataContext%2A> actual para un uso de <xref:System.Windows.Data.Binding.Path%2A>.  Si el enlace actualiza el origen, esa propiedad debe ser de lectura y escritura, y el objeto de origen debe ser mutable.  
  
<a name="singleindex"></a>   
### Indizador único en el objeto inmediato como contexto de datos  
  
```  
<Binding Path="[key]" .../>  
```  
  
 `key` debe ser el índice con tipo a un diccionario o tabla hash, o el índice de tipo entero de una matriz.  Además, el valor de la clave debe ser un tipo que se pueda enlazar directamente a la propiedad donde se aplica.  Por ejemplo, una tabla hash que contenga claves de cadena y valores de cadena se puede utilizar de este modo para enlazar a Text para un objeto <xref:System.Windows.Controls.TextBox>.  O bien, si la clave apunta a una colección o un subíndice, podría utilizar esta sintaxis para enlazar a una propiedad de la colección de destino.  De lo contrario, deberá hacer referencia a una propiedad concreta, mediante una sintaxis tal como `<Binding Path="[``key``].``propertyName``" .../>`.  
  
 Puede especificar el tipo del índice si es necesario.  Para obtener información detallada sobre este aspecto de una ruta de acceso de propiedad indizada, vea <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  
  
<a name="multipleindirect"></a>   
### Propiedad múltiple \(destino de propiedad indirecto\)  
  
```  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName` debe resolverse en el nombre de una propiedad que sea el objeto <xref:System.Windows.FrameworkElement.DataContext%2A>actual.  Las propiedades de ruta `propertyName` y `propertyName2` pueden ser cualquier propiedad que exista en una relación, donde `propertyName2` es una propiedad que existe en el tipo que es el valor de `propertyName`.  
  
<a name="singleattached"></a>   
### Propiedad única, adjunta o también calificada con el tipo  
  
```  
<object property="(ownerType.propertyName)" .../>  
```  
  
 Los paréntesis indican que esta propiedad en un objeto <xref:System.Windows.PropertyPath> se debe construir utilizando una calificación parcial.  Puede usar un espacio de nombres XML para encontrar el tipo con una asignación adecuada.  `ownerType` busca los tipos a los que tiene acceso un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], mediante las declaraciones <xref:System.Windows.Markup.XmlnsDefinitionAttribute> de cada ensamblado.  La mayoría de las aplicaciones tienen el espacio de nombres XML predeterminado asignado al espacio de nombres [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], por lo que solamente es necesario un prefijo, habitualmente, para tipos personalizados o que están fuera de ese espacio de nombres.  `propertyName` debe resolverse en el nombre de una propiedad que exista en el objeto `ownerType` actual.  Esta sintaxis se utiliza generalmente para uno de los casos siguientes:  
  
-   La ruta de acceso se especifica en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], que está en un estilo o plantilla que no tiene un tipo de destino especificado.  Generalmente, un uso certificado no es válido para otros casos distintos de éste, porque en los casos sin estilo ni plantilla la propiedad existe en una instancia, no en un tipo.  
  
-   La propiedad es una propiedad asociada.  
  
-   Está enlazando a una propiedad estática.  
  
 Para el uso como destino del guión gráfico, la propiedad especificada como `propertyName` debe ser un objeto <xref:System.Windows.DependencyProperty>.  
  
<a name="sourcetraversal"></a>   
### Exploración transversal de origen \(enlace a jerarquías de colecciones\)  
  
```  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 El carácter \/ de esta sintaxis se utiliza para navegar dentro de un objeto de origen de datos jerárquico; se admiten varios pasos en la jerarquía con caracteres \/ sucesivos.  La exploración transversal de origen tiene en cuenta la posición del puntero de registro actual, que se determina sincronizando los datos con la interfaz de usuario de su vista.  Para obtener detalles sobre el enlace con objetos de origen de datos jerárquicos y el concepto de puntero de registro actual en el enlace de datos, vea [Usar el patrón principal\-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) o [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  Superficialmente, esta sintaxis se parece a [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)].  Una expresión [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] verdadera para enlazar a un origen de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] no se utiliza como un valor <xref:System.Windows.Data.Binding.Path%2A> y se debe utilizar en su lugar para la propiedad <xref:System.Windows.Data.Binding.XPath%2A> mutuamente excluyente.  
  
### Vistas de colección  
 Para hacer referencia a una vista de colección con nombre, asigne el carácter hash \(`#`\) como prefijo del nombre de la vista de colección.  
  
### Puntero de registro actual  
 Para hacer referencia al indicador del registro actual para una vista de colección o detalle principal del escenario de enlace de datos, inicie la cadena de la ruta de acceso con una barra diagonal \(`/`\).  Cualquier ruta de acceso pasada la barra diagonal se atraviesa desde el puntero de registro actual.  
  
### Indizadores múltiples  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 Si un objeto determinado admite varios indizadores, esos indizadores se pueden especificar en orden, de manera similar a la sintaxis de referencia a una matriz.  El objeto en cuestión puede ser el contexto actual o el valor de una propiedad que contiene un objeto de índice múltiple.  
  
 De forma predeterminada, los valores del indizador tienen tipos que utilizan las características del objeto subyacente.  Puede especificar el tipo del índice si es necesario.  Para obtener detalles sobre cómo asignar tipos a los indizadores, vea <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  
  
<a name="mixing"></a>   
### Sintaxis mixtas  
 Las sintaxis antes mostradas puede intercalarse.  Por ejemplo, el siguiente es un ejemplo que crea una ruta de acceso de propiedad al color en una posición x, y determinada de una propiedad `ColorGrid` que contiene una matriz de cuadrícula de píxeles de objetos <xref:System.Windows.Media.SolidColorBrush>:  
  
```  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### Caracteres de escape para cadenas de ruta de acceso de propiedad  
 Para ciertos objetos de negocios, puede encontrarse un caso donde la cadena de ruta de acceso de propiedad requiere una secuencia de escape con el fin de analizar correctamente.  La necesidad de un mecanismo de escape no es habitual, puesto que muchos de estos caracteres tienen problemas similares de interacción de nombres en lenguajes que normalmente se utilizan para definir el objeto comercial.  
  
-   Dentro de los indizadores \(\[ \]\), el carácter de intercalación \(^\) es el carácter de escape para el carácter siguiente.  
  
-   Debe usar como identificador de escape \(mediante entidades XML\) ciertos caracteres que son especiales para la definición del lenguaje XML.  Utilice `&` como secuencia de escape para el carácter "&".  Utilice `>` como secuencia de escape de la etiqueta de cierre"\>".  
  
-   Debe usar como identificador de escape \(mediante caracteres de barra diagonal inversa `\`\) caracteres que son especiales para el comportamiento del analizador XAML de WPF para procesar una extensión de marcado.  
  
    -   La barra diagonal inversa \(`\`\) es el propio carácter de escape.  
  
    -   El signo igual \(`=`\) separa el nombre de propiedad del valor de propiedad.  
  
    -   La coma \(`,`\) separa las propiedades.  
  
    -   La llave de cierre \(`}`\) es el fin de una extensión de marcado.  
  
> [!NOTE]
>  Técnicamente, estos escapes también funcionan para una ruta de acceso de propiedad de guión gráfico, pero normalmente se recorren modelos de objetos para los objetos WPF existentes y no es necesario establecer secuencias de escape.  
  
<a name="databinding_sa"></a>   
## PropertyPath para destinos de animación  
 La propiedad de destino de una animación debe ser una [propiedad de dependencia](GTMT) que admite un objeto <xref:System.Windows.Freezable> o un tipo primitivo.  Sin embargo, la propiedad de destino de un tipo y la propiedad animada final pueden existir en objetos diferentes.  Para las animaciones, se utiliza una ruta de acceso de propiedad se utiliza para definir la conexión entre la propiedad del objeto de destino de animación con nombre y la propiedad de animación de destino deseada, explorando transversalmente relaciones de objeto\-propiedad en los valores de propiedad.  
  
<a name="general"></a>   
### Consideraciones generales sobre objeto\-propiedad para animaciones  
 Para obtener más información sobre conceptos de animación en general, vea [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) y [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 El tipo de valor de la propiedad que se está animando debe ser un tipo <xref:System.Windows.Freezable> o uno primitivo.  La propiedad que inicia la ruta de acceso debe resolverse en el nombre de una [propiedad de dependencia](GTMT) que existe en el tipo <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> especificado.  
  
 Para permitir la clonación para animar un objeto <xref:System.Windows.Freezable> que ya está inmovilizado, el objeto especificado por <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> debe ser de una clase derivada de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
<a name="singlestepanim"></a>   
### Propiedad única en el objeto de destino  
  
```  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName` debe resolverse en el nombre de una [propiedad de dependencia](GTMT) que existe en el tipo <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> especificado.  
  
<a name="indirectanim"></a>   
### Establecimiento indirecto de destinos de propiedad  
  
```  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName` debe ser una propiedad que sea un tipo de valor <xref:System.Windows.Freezable> o un tipo primitivo, que exista en el tipo <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> especificado.  
  
 `propertyName2` debe ser el nombre de una [propiedad de dependencia](GTMT) que exista en el objeto que es el valor de `propertyName`.  En otras palabras, `propertyName2` debe existir como una propiedad de dependencia en el tipo que es `propertyName`<xref:System.Windows.DependencyProperty.PropertyType%2A>.  
  
 La asignación indirecta de destino de animaciones es necesaria debido a los estilos y plantillas aplicados.  Para usar como destino una animación, se necesita una propiedad <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> en un objeto de destino; [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md) o <xref:System.Windows.FrameworkElement.Name%2A> establecen ese nombre.  Aunque los elementos de plantilla y estilo también pueden tener nombres, esos nombres solamente son válidos dentro del ámbito de nombres del estilo y de la plantilla.  \(Si las plantillas y los estilos compartieran ámbitos de nombres con el marcado de la aplicación, los nombres no podrían ser únicos.  Los estilos y las plantillas se comparten literalmente entre las instancias y perpetuarían nombres duplicados.\) Así, si las propiedades individuales de un elemento que quizá desee animar proceden de un estilo o de una plantilla, deberá empezar con una instancia de elemento con nombre que no proceda de una plantilla de estilo y, a continuación, dirigirse al árbol visual de estilos o de plantillas para llegar a la propiedad que desea animar.  
  
 Por ejemplo, la propiedad <xref:System.Windows.Controls.Panel.Background%2A> de un objeto <xref:System.Windows.Controls.Panel> es un objeto <xref:System.Windows.Media.Brush> completo \(realmente, un objeto <xref:System.Windows.Media.SolidColorBrush>\) procedente de una plantilla de tema.  Para animar completamente un objeto <xref:System.Windows.Media.Brush>, debería haber un tipo BrushAnimation \(probablemente uno para cada tipo de <xref:System.Windows.Media.Brush> \) y tal tipo no existe.  Para animar un objeto Brush, en su lugar se animan las propiedades de un tipo <xref:System.Windows.Media.Brush> determinado.  Necesita ir de un objeto <xref:System.Windows.Media.SolidColorBrush> a su propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> para aplicar allí un objeto <xref:System.Windows.Media.Animation.ColorAnimation>.  La ruta de acceso de propiedad para este ejemplo sería `Background.Color`.  
  
<a name="attachedanim"></a>   
### Propiedades adjuntas  
  
```  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 Los paréntesis indican que esta propiedad en un objeto <xref:System.Windows.PropertyPath> se debe construir utilizando una calificación parcial.  Puede utilizar un espacio de nombres XML para buscar el tipo.  `ownerType` busca los tipos a los que tiene acceso un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], mediante las declaraciones <xref:System.Windows.Markup.XmlnsDefinitionAttribute> de cada ensamblado.  La mayoría de las aplicaciones tienen el espacio de nombres XML predeterminado asignado al espacio de nombres [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], por lo que solamente es necesario un prefijo, habitualmente, para tipos personalizados o que están fuera de ese espacio de nombres.  `propertyName` debe resolverse en el nombre de una propiedad que exista en el objeto `ownerType` actual.  La propiedad especificada como `propertyName` debe ser un objeto <xref:System.Windows.DependencyProperty>.  \(Todas las propiedades asociadas a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementan como propiedades de dependencia, por lo que este problema sólo afecta a las propiedades asociadas personalizadas.\)  
  
<a name="indexanim"></a>   
### Indizadores  
  
```  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 La mayoría de las propiedades de dependencia y de los tipos <xref:System.Windows.Freezable> no admiten un indizador.  Por consiguiente, el único uso para un indizador en una ruta de acceso de animación está en una posición intermedia entre la propiedad que inicia la cadena en el destino con nombre y la propiedad animada final.  En la sintaxis que se proporciona, eso corresponde a `propertyName2`.  Por ejemplo, podría ser necesario el uso del indizador si la propiedad intermedia es una colección como <xref:System.Windows.Media.TransformGroup>, en una ruta de acceso de propiedad como `RenderTransform.Children[1].Angle`.  
  
<a name="ppincode"></a>   
## PropertyPath en código  
 El uso de código para <xref:System.Windows.PropertyPath>, incluido cómo construir un objeto <xref:System.Windows.PropertyPath>, se documenta en el tema de referencia para <xref:System.Windows.PropertyPath>.  
  
 En general, <xref:System.Windows.PropertyPath> se ha diseñado para utilizar dos constructores diferentes, uno para los usos de enlace y los usos de animación más simples, y otro para los usos de animación complejos.  Utilice la firma <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> para los usos de enlace, donde el objeto es una cadena.  Utilice la firma <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> para rutas de acceso de animación de un paso, donde el objeto es un objeto <xref:System.Windows.DependencyProperty>.  Utilice la firma [PropertyPath\(String, Object\<xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> para las animaciones complejas.  Este último constructor utiliza una cadena de token para el primer parámetro y una matriz de objetos que rellenan posiciones en la cadena de token para definir una relación de ruta de acceso de propiedad.  
  
## Vea también  
 <xref:System.Windows.PropertyPath>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)