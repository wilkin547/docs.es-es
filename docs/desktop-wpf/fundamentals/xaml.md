---
title: Información general sobre XAML
description: Obtenga información sobre la estructura e implementación del lenguaje XAML en Windows Presentation Foundation (WPF) para .NET Core.
author: adegeo
ms.date: 08/08/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interfaces [XAML]
- classes [XAML]
- root element [XAML]
- XAML [WPF], about XAML
- base classes [XAML]
- routed events [WPF]
- code-behind files [WPF], XAML
- collection properties [XAML]
- events [XAML]
- property element [XAML]
- content models [XAML]
- Extensible Application Markup Language (see XAML)
- attribute syntax [XAML]
ms.openlocfilehash: 4ccf107bd56be33d9b195d97ae5edf1a6b85117f
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325697"
---
# <a name="xaml-overview-in-wpf"></a>Información general sobre XAML en WPF

En este artículo se describen las características del lenguaje XAML y se muestra cómo usarlo para escribir aplicaciones para Windows Presentation Foundation (WPF). En concreto, en este artículo se describe XAML como lo implementa WPF. El propio XAML es un concepto de lenguaje más amplio que WPF.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>Qué es XAML

XAML es un lenguaje declarativo de marcado. Como se aplica al modelo de programación de .NET Core, XAML simplifica la creación de una interfaz de usuario para una aplicación .NET Core. Puede crear elementos visibles de la interfaz de usuario en el marcado declarativo de XAML y, después, separar la definición de la interfaz de usuario de la lógica en tiempo de ejecución con archivos de código subyacente que se unen al marcado mediante definiciones de clases parciales. XAML representa directamente la creación de instancias de objetos en un conjunto concreto de tipos de respaldo definidos en ensamblados. Esto no es lo que sucede con la mayoría de lenguajes de marcado, que normalmente se interpretan sin esa relación directa con un sistema de tipos de respaldo. XAML habilita un flujo de trabajo en el que partes independientes pueden funcionar en la interfaz de usuario y la lógica de una aplicación, mediante herramientas potencialmente distintas.

Cuando se representan como texto, los archivos XAML son archivos XML que generalmente tienen la extensión `.xaml`. Los archivos se pueden codificar con cualquier codificación XML, pero lo habitual es la codificación UTF-8.

En el ejemplo siguiente se muestra cómo podría crear un botón como parte de una interfaz de usuario. Este ejemplo se ha pensado para que tenga una idea de cómo XAML representa metáforas de programación de interfaz de usuario comunes (no es un ejemplo completo).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>Resumen de la sintaxis de XAML

En las secciones siguientes se explican las formas básicas de la sintaxis XAML y se proporciona un breve ejemplo de marcado. Estas secciones no están pensadas para proporcionar información completa sobre cada sintaxis, por ejemplo, cómo se representan en el sistema de tipos de respaldo. Para obtener más información sobre los conceptos específicos de XAML, vea [Detalles de la sintaxis XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

Gran parte del material de las secciones siguientes le parecerá básico si ya está familiarizado con el lenguaje XML. Esta es una consecuencia de uno de los principios de diseño básicos de XAML. El lenguaje XAML define conceptos propios, pero que funcionan dentro del lenguaje XML y del formato de marcado.

### <a name="xaml-object-elements"></a>Elementos de objeto XAML

Normalmente, un elemento de objeto declara una instancia de un tipo. Ese tipo se define en los ensamblados a los que hace referencia la tecnología que usa XAML como un lenguaje.

La sintaxis del elemento de objeto siempre se inicia con un corchete angular de apertura (`<`). Este va seguido del nombre del tipo donde quiere crear una instancia. (El nombre puede incluir un prefijo, un concepto que se explicará más adelante). Después de esto, puede declarar opcionalmente los atributos en el elemento de objeto. Para completar la etiqueta del elemento de objeto, finalice con un corchete angular de cierre (`>`). En su lugar, puede usar un formato de autocierre sin contenido y completar la etiqueta con una barra diagonal y un corchete angular de cierre (`/>`) seguidos. Por ejemplo, examine de nuevo el fragmento de código de marcado que se ha mostrado antes.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

Esto especifica dos elementos de objeto: `<StackPanel>` (con contenido y una etiqueta de cierre después) y `<Button .../>` (el formulario de autocierre, con varios atributos). Los elementos de objeto `StackPanel` y `Button` se asignan al nombre de una clase definida por WPF y que forma parte de los ensamblados de WPF. Al especificar una etiqueta de elemento de objeto, se crea una instrucción para que el procesamiento XAML cree una instancia del tipo subyacente. Para crear cada instancia, se llama al constructor predeterminado del tipo subyacente al analizar y cargar el código XAML.

### <a name="attribute-syntax-properties"></a>Sintaxis de atributo (propiedades)

Las propiedades de un objeto se pueden expresar a menudo como atributos del elemento de objeto. La sintaxis de atributo denomina la propiedad de objeto que se va a establecer, seguida del operador de asignación (=). El valor de un atributo siempre se especifica como una cadena incluida entre comillas.

La sintaxis de atributo es la sintaxis de establecimiento de propiedades más optimizada y será la más intuitiva para los desarrolladores que han usado lenguajes de marcado anteriormente. Por ejemplo, el marcado siguiente crea un botón que tiene texto rojo y un fondo azul, además de mostrar texto especificado como `Content`.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>Sintaxis de elementos de propiedad

En algunas propiedades de un elemento de objeto, no es posible usar la sintaxis de atributo, ya que el objeto o la información necesaria para proporcionar el valor de propiedad no se puede expresar correctamente dentro de las comillas y restricciones de cadena de la sintaxis de atributo. En estos casos, se puede usar otra sintaxis conocida como sintaxis de elementos de propiedad.

La sintaxis de la etiqueta inicial del elemento de propiedad es `<TypeName.PropertyName>`. Por lo general, el contenido de esa etiqueta es un elemento de objeto del tipo que la propiedad toma como su valor. Después de especificar el contenido, debe cerrar el elemento de propiedad con una etiqueta final. La sintaxis de la etiqueta final es `</TypeName.PropertyName>`.

Si es posible usar una sintaxis de atributo, su uso es generalmente más conveniente, ya que habilita un marcado más compacto, pero suele ser una cuestión de estilo, no una limitación técnica. En el ejemplo siguiente se muestra cómo se establecen las mismas propiedades que en el ejemplo anterior de sintaxis de atributo, pero ahora usando la sintaxis de elementos de propiedad para todas las propiedades de `Button`.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>Sintaxis de colecciones

El lenguaje XAML incluye algunas optimizaciones que generan un marcado más legible. Una de estas optimizaciones consiste en que si una propiedad determinada toma un tipo de colección, entonces los elementos que se declaran en el marcado como elementos secundarios dentro del valor de esa propiedad se convierten en parte de la colección. En este caso, una colección de elementos de objeto secundarios es el valor que se establece para la propiedad de la colección.

En el ejemplo siguiente se muestra la sintaxis de colección para establecer los valores de la propiedad <xref:System.Windows.Media.GradientBrush.GradientStops%2A>.

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.GradientStops>
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->
    <GradientStop Offset="0.0" Color="Red" />
    <GradientStop Offset="1.0" Color="Blue" />
  </LinearGradientBrush.GradientStops>
</LinearGradientBrush>
```

### <a name="xaml-content-properties"></a>Propiedades de contenido XAML

XAML especifica una característica del lenguaje por la que una clase puede designar exactamente una de sus propiedades para que sea la propiedad de _contenido_ de XAML. Los elementos secundarios de ese elemento de objeto se usan para establecer el valor de esa propiedad de contenido. Es decir, únicamente para la propiedad de contenido, puede omitir un elemento de propiedad cuando se establece esa propiedad en marcado XAML y genera una metáfora de elemento primario/secundario más visible en el marcado.

Por ejemplo, <xref:System.Windows.Controls.Border> especifica una propiedad de _contenido_ de <xref:System.Windows.Controls.Decorator.Child%2A>. Los dos elementos <xref:System.Windows.Controls.Border> siguientes se tratan de la misma forma. El primero se aprovecha de la sintaxis de la propiedad de contenido y omite el elemento de propiedad `Border.Child`. El segundo muestra `Border.Child` explícitamente.

```xaml
<Border>
  <TextBox Width="300"/>
</Border>
<!--explicit equivalent-->
<Border>
  <Border.Child>
    <TextBox Width="300"/>
  </Border.Child>
</Border>
```

Como regla del lenguaje XAML, el valor de una propiedad de contenido de XAML se debe proporcionar exclusivamente antes o después de cualquier otro elemento de propiedad en ese elemento de objeto. Por ejemplo, el marcado siguiente no se compila.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

Para obtener más información sobre los conceptos específicos de XAML, vea [Detalles de la sintaxis XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

### <a name="text-content"></a>Contenido de texto

Un pequeño número de elementos de código XAML puede procesar directamente el texto como su contenido. Para habilitar esto, debe cumplirse una de estas situaciones:

- La clase debe declarar una propiedad de contenido y esa propiedad de contenido debe ser de un tipo asignable a una cadena (podría ser <xref:System.Object>). Por ejemplo, cualquier objeto <xref:System.Windows.Controls.ContentControl> usa <xref:System.Windows.Controls.ContentControl.Content%2A> como su propiedad de contenido y es de tipo <xref:System.Object>, y esto admite el uso siguiente en un objeto <xref:System.Windows.Controls.ContentControl> como <xref:System.Windows.Controls.Button>: `<Button>Hello</Button>`.

- El tipo debe declarar un convertidor de tipos, en cuyo caso el contenido de texto se usa como texto de inicialización para ese convertidor de tipos. Por ejemplo, `<Brush>Blue</Brush>` convierte el valor de contenido de `Blue` en un pincel. Este caso es menos común en la práctica.

- El tipo debe ser una primitiva conocida del lenguaje XAML.

### <a name="content-properties-and-collection-syntax-combined"></a>Propiedades de contenido y sintaxis de colección combinadas

Considere este ejemplo.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

Aquí, cada instancia de <xref:System.Windows.Controls.Button> es un elemento secundario de <xref:System.Windows.Controls.StackPanel>. Este es un marcado optimizado e intuitivo que omite dos etiquetas por dos razones diferentes.

- **Elemento de propiedad StackPanel.Children omitido:** <xref:System.Windows.Controls.StackPanel> se deriva de <xref:System.Windows.Controls.Panel>. <xref:System.Windows.Controls.Panel> define <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> como su propiedad de contenido XAML.

- **Elemento de objeto UIElementCollection omitido:** la propiedad <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> toma el tipo <xref:System.Windows.Controls.UIElementCollection>, que implementa <xref:System.Collections.IList>. Se puede omitir la etiqueta de elemento de la colección, según las reglas de XAML para el procesamiento de colecciones como <xref:System.Collections.IList>. (En este caso, en realidad no se puede crear una instancia de <xref:System.Windows.Controls.UIElementCollection>, ya que no expone un constructor sin parámetros y, por eso, el elemento de objeto <xref:System.Windows.Controls.UIElementCollection> se marca como comentario).

```xaml
<StackPanel>
  <StackPanel.Children>
    <!--<UIElementCollection>-->
    <Button>First Button</Button>
    <Button>Second Button</Button>
    <!--</UIElementCollection>-->
  </StackPanel.Children>
</StackPanel>
```

### <a name="attribute-syntax-events"></a>Sintaxis de atributos (eventos)

La sintaxis de atributos también se puede usar para los miembros que son eventos en lugar de propiedades. En este caso, el nombre del atributo es el nombre del evento. En la implementación WPF de eventos para XAML, el valor del atributo es el nombre de un controlador que implementa el delegado de ese evento. Por ejemplo, en el marcado siguiente se asigna un controlador para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> a un objeto <xref:System.Windows.Controls.Button> creado en el marcado:

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

En WPF, los eventos y el código XAML son más complejos que este ejemplo de la sintaxis de atributos. Por ejemplo, podría preguntarse qué representa el elemento `ClickHandler` al que se hace referencia aquí y cómo se define. Esto se explicará en la próxima sección [Eventos y código XAML subyacente](#events-and-xaml-code-behind) de este artículo.

## <a name="case-and-white-space-in-xaml"></a>Uso de mayúsculas y minúsculas, y espacio en blanco en XAML

En general, XAML distingue mayúsculas de minúsculas. Para resolver los tipos de respaldo, XAML de WPF distingue mayúsculas de minúsculas mediante las mismas reglas que el CLR. Los elementos de objeto, los elementos de propiedad y los nombres de atributo se deben especificar usando la grafía que distinga mayúsculas de minúsculas cuando se comparan por nombre con el tipo subyacente en el ensamblado, o con un miembro de un tipo. Las palabras clave y las primitivas del lenguaje XAML también distinguen mayúsculas de minúsculas. Los valores no siempre distinguen mayúsculas de minúsculas. La distinción entre mayúsculas y minúsculas para los valores dependerá del comportamiento del convertidor de tipos asociado a la propiedad que toma el valor o del tipo de valor de propiedad. Por ejemplo, las propiedades que toman el tipo <xref:System.Boolean> pueden tomar `true` o `True` como valores equivalentes, pero solo porque la conversión de tipos del analizador de código XAML de WPF nativo de cadena a <xref:System.Boolean> ya los permite como equivalentes.

Los procesadores y serializadores XAML de WPF omiten o quitan todos los espacios en blanco no significativos y normalizan cualquier espacio en blanco significativo. Esto es coherente con las recomendaciones de comportamiento del espacio en blanco predeterminado de la especificación de XAML. Este comportamiento solo tiene importancia si se especifican cadenas dentro de propiedades de contenido de XAML. Es decir, XAML convierte los caracteres de espacio, avance de línea y tabulación en espacios y, después, conserva un espacio si lo encuentra en cualquier extremo de una cadena contigua. La explicación completa del control del espacio en blanco de XAML no se aborda en este artículo. Para obtener más información, vea [Procesamiento del espacio en blanco en XAML](../xaml-services/white-space-processing.md).

## <a name="markup-extensions"></a>Extensiones de marcado

Las extensiones de marcado son un concepto del lenguaje XAML. Cuando se usan para proporcionar el valor de una sintaxis de atributos, las llaves (`{` y `}`) indican el uso de una extensión de marcado. Este uso hace que el procesamiento XAML se aparte del tratamiento general de valores de atributo como una cadena literal o un valor directamente convertible en cadena.

Las extensiones de marcado más comunes que se usan en la programación de aplicaciones WPF son [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md) (para las expresiones de enlace de datos) y las referencias de recursos [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) y [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Al usar las extensiones de marcado, puede usar la sintaxis de atributos para proporcionar valores para las propiedades aunque esa propiedad no admita una sintaxis de atributos en general. Las extensiones de marcado suelen usar tipos de expresión intermedios para habilitar características como diferir los valores o hacer referencia a otros objetos que solo están presentes en tiempo de ejecución.

Por ejemplo, en el marcado siguiente se establece el valor de la propiedad <xref:System.Windows.FrameworkElement.Style%2A> mediante la sintaxis de atributo. La propiedad <xref:System.Windows.FrameworkElement.Style%2A> toma una instancia de la clase <xref:System.Windows.Style> de la que, de forma predeterminada, no se puede crear una instancia mediante una cadena de sintaxis de atributo. Pero, en este caso, el atributo hace referencia a una extensión de marcado concreta, `StaticResource`. Cuando se procesa dicha extensión de marcado, devuelve una referencia a un estilo del que ya se han creado instancias como un recurso con clave en un diccionario de recursos.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

Para obtener una lista de referencias de todas las extensiones de marcado para XAML implementadas específicamente en WPF, vea [Extensiones XAML de WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md). Para obtener una lista de referencias de las extensiones de marcado definidas por System.Xaml y que más se usan para las implementaciones XAML de .NET Framework, vea [Características del lenguaje del espacio de nombres de XAML (x:)](../xaml-services/namespace-language-features.md). Para obtener más información sobre los conceptos de la extensión de marcado, vea [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="type-converters"></a>Convertidores de tipos

En la sección [Resumen de sintaxis de XAML](#xaml-syntax-in-brief), se ha mencionado que el valor de atributo debe poder establecerlo una cadena. El control nativo básico de cómo se convierten las cadenas en otros tipos de objeto o valores primitivos se basa en el propio tipo <xref:System.String>, además del procesamiento nativo para tipos concretos como <xref:System.DateTime> o <xref:System.Uri>. Pero muchos tipos de WPF o miembros de esos tipos extienden el comportamiento básico del procesamiento de atributos de cadena, de forma que se pueden especificar instancias de tipos de objeto más complejos como cadenas y atributos.

La estructura <xref:System.Windows.Thickness> es un ejemplo de un tipo que incluye una conversión de tipos habilitada para los usos de XAML. <xref:System.Windows.Thickness> indica las medidas dentro de un rectángulo anidado y se usa como valor para propiedades como <xref:System.Windows.FrameworkElement.Margin%2A>. Al colocar un convertidor de tipos en <xref:System.Windows.Thickness>, todas las propiedades que usan una instancia de <xref:System.Windows.Thickness> son más fáciles de especificar en XAML porque se pueden especificar como atributos. En el ejemplo siguiente se usa una conversión de tipos y una sintaxis de atributo para proporcionar un valor a una instancia de <xref:System.Windows.FrameworkElement.Margin%2A>:

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

El ejemplo de sintaxis de atributo anterior es equivalente al ejemplo de sintaxis siguiente más detallado, donde la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> se establece mediante la sintaxis de elementos de propiedad que contiene un elemento de objeto <xref:System.Windows.Thickness>. Las cuatro propiedades clave de <xref:System.Windows.Thickness> se establecen como atributos en la nueva instancia:

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> También hay un número limitado de objetos en los que la conversión de tipos es la única manera pública de establecer una propiedad en ese tipo sin necesidad de una subclase, ya que el propio tipo no tiene un constructor sin parámetros. Un ejemplo es <xref:System.Windows.Input.Cursor>.

Para obtener más información sobre la conversión de tipos, vea [Clases TypeConverter y XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

## <a name="xaml-root-elements-and-xaml-namespaces"></a>Elementos raíz y espacios de nombres de XAML

Para que un archivo XAML pueda ser tanto un archivo XML con formato correcto como un archivo XAML válido, solo debe tener un elemento raíz. En escenarios de WPF típicos, se usa un elemento raíz que tiene un significado destacado en el modelo de aplicación de WPF (por ejemplo, <xref:System.Windows.Window> o <xref:System.Windows.Controls.Page> para una página, <xref:System.Windows.ResourceDictionary> para un diccionario externo, o bien <xref:System.Windows.Application> para la definición de la aplicación). En el ejemplo siguiente se muestra el elemento raíz de un archivo XAML típico para una página de WPF, con el elemento raíz de <xref:System.Windows.Controls.Page>.

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

El elemento raíz también contiene los atributos `xmlns` y `xmlns:x`. Estos atributos indican a un procesador XAML los espacios de nombres XAML que contienen las definiciones de tipo de los tipos de respaldo a los que el marcado hará referencia como elementos. El atributo `xmlns` indica específicamente el espacio de nombres XAML predeterminado. Dentro del espacio de nombres XAML predeterminado, los elementos de objeto en el marcado se pueden especificar sin un prefijo. En la mayoría de los escenarios de aplicaciones WPF y para casi todos los ejemplos que se proporcionan en las secciones sobre WPF del SDK, el espacio de nombres de XAML predeterminado se asigna al espacio de nombres `http://schemas.microsoft.com/winfx/2006/xaml/presentation` de WPF. El atributo `xmlns:x` indica un espacio de nombres XAML adicional, que asigna el espacio de nombres del lenguaje XAML `http://schemas.microsoft.com/winfx/2006/xaml`.

Este uso de `xmlns` para definir un ámbito para el uso y asignación de un ámbito de nombres es coherente con la especificación XML 1.0. Los ámbitos de nombres de código XAML solo se diferencian de los ámbitos de nombres de XML en que un ámbito de nombres de código XAML también implica a la forma en que los tipos respaldan los elementos del ámbito de nombres cuando se trata de la resolución de tipos y del análisis del código XAML.

Los atributos `xmlns` solo son estrictamente necesarios en el elemento raíz de cada archivo XAML. Las definiciones de `xmlns` se aplicarán a todos los elementos descendientes del elemento raíz (una vez más, este comportamiento es coherente con la especificación XML 1.0 para `xmlns`). También se permiten atributos `xmlns` en otros elementos bajo la raíz, y se aplican a cualquier elemento descendiente del elemento de definición. En cambio, una definición o redefinición frecuente de los espacios de nombres XAML puede dar lugar a un estilo de marcado XAML que resulte difícil de leer.

La implementación de WPF de su procesador XAML incluye una infraestructura que reconoce los ensamblados básicos de WPF. Se sabe que los ensamblados básicos de WPF contienen los tipos que admiten las asignaciones de WPF al espacio de nombres XAML predeterminado. Esto se habilita a través de la configuración que forma parte de su archivo de compilación de proyecto y los sistemas de compilación y proyectos de WPF. Por tanto, solo es necesario declarar el espacio de nombres XAML predeterminado como `xmlns` para hacer referencia a los elementos de código XAML que proceden de los ensamblados de WPF.

### <a name="the-x-prefix"></a>El prefijo x:

En el ejemplo de elemento raíz anterior, el prefijo `x:` se ha usado para asignar el espacio de nombres XAML `http://schemas.microsoft.com/winfx/2006/xaml`, que es el espacio de nombres XAML dedicado que admite las construcciones de lenguaje XAML. Este prefijo `x:` se usa para asignar este espacio de nombres XAML en las plantillas de los proyectos, en los ejemplos y en la documentación de este SDK. El espacio de nombres XAML para el lenguaje XAML contiene varias construcciones de programación que usará con frecuencia en el código XAML. A continuación se muestra una lista de las construcciones de programación del prefijo `x:` más comunes que usará:

- [x:Key](../xaml-services/xkey-directive.md): establece una clave única para cada recurso en un objeto <xref:System.Windows.ResourceDictionary> (o conceptos de diccionario similares en otros marcos). Probablemente `x:Key` representará el 90 % de los usos de `x:` que verá en el marcado de una aplicación WPF típica.

- [x:Class](../xaml-services/xclass-directive.md): especifica el espacio de nombres del CLR y el nombre de la clase que proporciona código subyacente para una página XAML. Debe disponer de esta clase para admitir el código subyacente por el modelo de programación WPF; por esto casi siempre verá `x:` asignado, aunque no haya ningún recurso.

- [x:Name](../xaml-services/xname-directive.md): especifica un nombre de objeto en tiempo de ejecución para la instancia que existe en el código en tiempo de ejecución después de procesar un elemento de objeto. En general, usará frecuentemente una propiedad equivalente definida por WPF para [x:Name](../xaml-services/xname-directive.md). Esas propiedades se asignan específicamente a una propiedad de respaldo de CLR y así son más útiles para la programación de aplicaciones, donde frecuentemente se usa código de tiempo de ejecución para encontrar los elementos con nombre a partir del código XAML inicializado. La propiedad más común de este tipo es <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>. Es posible que todavía use [x:Name](../xaml-services/xname-directive.md) cuando la propiedad <xref:System.Windows.FrameworkElement.Name%2A> del nivel de marco WPF equivalente no se admite en un tipo concreto. Esto sucede en ciertos escenarios de animación.

- [x:Static](../xaml-services/xstatic-markup-extension.md): habilita una referencia que obtiene un valor estático que, de lo contrario, no sería una propiedad compatible con XAML.

- [x:Type](../xaml-services/xtype-markup-extension.md): crea una referencia de <xref:System.Type> basada en un nombre de tipo. Esto se usa para especificar atributos que toman <xref:System.Type>, como <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>, aunque con frecuencia la propiedad dispone de una conversión de cadena a <xref:System.Type> nativa y el uso de la extensión de marcado [x:Type](../xaml-services/xtype-markup-extension.md) es opcional.

Hay construcciones de programación adicionales en el prefijo o espacio de nombres XAML `x:` que no son tan habituales. Para obtener más información, vea [Características del lenguaje del espacio de nombres de XAML (x:)](../xaml-services/namespace-language-features.md).

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Prefijos y tipos personalizados en XAML

Para los ensamblados personalizados propios o para los que son externos al núcleo WPF de **PresentationCore**, **PresentationFramework** y **WindowsBase**, puede especificar el ensamblado como parte de una asignación de `xmlns` personalizada. Después, puede hacer referencia a los tipos de ese ensamblado en su código XAML, siempre que su tipo esté implementado correctamente para admitir los usos de código XAML que intenta.

El siguiente es un ejemplo básico de cómo funcionan los prefijos personalizados en el marcado XAML. El prefijo `custom` se define en la etiqueta de elemento raíz y se asigna a un ensamblado concreto que se empaqueta y está disponible con la aplicación. Este ensamblado contiene un tipo `NumericUpDown`, que se implementa para admitir el uso XAML general, además de usar una herencia de clases que permite su inserción en este punto concreto en un modelo de contenido de código XAML de WPF. Se declara una instancia de este control `NumericUpDown` como un elemento de objeto, usando el prefijo para que un analizador de código XAML sepa qué espacio de nombres XAML contiene el tipo y, por consiguiente, dónde está el ensamblado de respaldo que contiene la definición de tipo.

```xaml
<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"
    >
  <StackPanel Name="LayoutRoot">
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>
...
  </StackPanel>
</Page>
```

Para obtener más información sobre los tipos personalizados en el código XAML, vea [Clases XAML y personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).

Para obtener más información sobre la relación existente entre los espacios de nombres XML y los del código en ensamblados, vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

## <a name="events-and-xaml-code-behind"></a>Eventos y código XAML subyacente

La mayoría de las aplicaciones WPF constan de marcado XAML y código subyacente. En un proyecto, el código XAML se escribe como un archivo `.xaml` y se usa un lenguaje de CLR, como Microsoft Visual Basic o C#, para escribir un archivo de código subyacente. Cuando se compila un archivo XAML como parte de los modelos de aplicaciones y programación de WPF, la ubicación del archivo de código subyacente XAML para cada archivo XAML se identifica especificando un espacio de nombres y una clase como el atributo `x:Class` del elemento raíz de XAML.

En los ejemplos presentados hasta ahora se incluían varios botones, pero ninguno de ellos tenía todavía ningún comportamiento lógico asociado. El mecanismo primario en el nivel de la aplicación para agregar un comportamiento a un elemento de objeto consiste en usar un evento existente de la clase de elemento y escribir un controlador específico para ese evento que se invocará cuando este se genere en tiempo de ejecución. El nombre del evento y el nombre del controlador que se van a usar se especifican en el marcado, mientras que el código que implementa el controlador se define en el código subyacente.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

Tenga en cuenta que el archivo de código subyacente usa el espacio de nombres CLR `ExampleNamespace` y declara `ExamplePage` como una clase parcial dentro de dicho espacio de nombres. Esto es similar al valor de atributo `x:Class` de `ExampleNamespace`.`ExamplePage` que se ha proporcionado en la raíz del marcado. El compilador de marcado WPF creará una clase parcial para cualquier archivo XAML compilado, al derivar una clase del tipo de elemento raíz. Al proporcionar código subyacente que también define la misma clase parcial, el código resultante se combina dentro del mismo espacio de nombres y la clase de la aplicación compilada.

Para obtener más información sobre los requisitos para la programación de código subyacente en WPF, vea [Requisitos del código subyacente, los controladores de eventos y las clases parciales en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf).

Si no quiere crear un archivo de código subyacente independiente, también puede insertar el código dentro de un archivo XAML. En cambio, el código insertado es una técnica menos versátil que tiene importantes limitaciones. Para obtener más información, vea [Código subyacente y XAML en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

### <a name="routed-events"></a>Eventos enrutados

Una característica especial de los eventos que es fundamental para WPF es un evento enrutado. Los eventos enrutados permiten a un elemento controlar un evento generado por otro elemento diferente, siempre que dichos elementos estén relacionados entre sí a través de un árbol. Al especificar el control de eventos con un atributo XAML, se puede escuchar y controlar el evento enrutado en cualquier elemento, incluidos los elementos que no contienen ese evento concreto en la tabla de miembros de clase. Esto se consigue calificando el atributo de nombre de evento con el nombre de la clase propietaria. Por ejemplo, el elemento primario `StackPanel` en el ejemplo de `StackPanel` / `Button` actual podría registrar un controlador para el evento de botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del elemento secundario mediante la especificación del atributo `Button.Click` en el elemento de objeto `StackPanel`, con el nombre del controlador como valor de atributo. Para obtener más información, vea [Información general sobre eventos enrutados](../../framework/wpf/advanced/routed-events-overview.md).

## <a name="xaml-named-elements"></a>Elementos XAML con nombre

De manera predeterminada, la instancia de objeto que se crea en un gráfico de objetos al procesar un elemento de objeto XAML no posee un identificador único o una referencia de objeto. Por el contrario, si llama a un constructor en el código, casi siempre usa el resultado del constructor para establecer una variable en la instancia creada, de manera que pueda hacer referencia a dicha instancia posteriormente en el código. Para proporcionar acceso normalizado a los objetos creados mediante una definición de marcado, XAML define el [atributo x:Name](../xaml-services/xname-directive.md). Es posible establecer el valor del atributo `x:Name` en cualquier elemento de objeto. En el código subyacente, el identificador elegido es equivalente a una variable de instancia que hace referencia a la instancia creada. En todos los sentidos, los elementos con nombre funcionan como si fueran instancias de objeto (el nombre hace referencia a la instancia) y el código subyacente puede hacer referencia a los elementos con nombre para controlar las interacciones en tiempo de ejecución dentro de la aplicación. Esta conexión entre las instancias y las variables se logra por el compilador de marcado XAML de WPF y, más específicamente, implica características y modelos como <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> que no se describirán en este artículo.

Los elementos de código XAML del nivel de marco de WPF heredan una propiedad <xref:System.Windows.FrameworkElement.Name%2A>, que es equivalente al atributo `x:Name` definido por XAML. Otras clases también proporcionan equivalentes en el nivel de propiedad para `x:Name`, que en general también suele definirse como una propiedad `Name`. En general, si no puede localizar una propiedad `Name` en la tabla de miembros del elemento/tipo elegido, use `x:Name` en su lugar. Los valores `x:Name` proporcionarán un identificador a un elemento XAML que se puede usar en tiempo de ejecución por subsistemas concretos o por métodos de utilidad como <xref:System.Windows.FrameworkElement.FindName%2A>.

En el ejemplo siguiente se establece <xref:System.Windows.FrameworkElement.Name%2A> en un elemento <xref:System.Windows.Controls.StackPanel>. Después, un controlador en un objeto <xref:System.Windows.Controls.Button> dentro de <xref:System.Windows.Controls.StackPanel> hace referencia a <xref:System.Windows.Controls.StackPanel> a través de su referencia de instancia `buttonContainer` establecida por <xref:System.Windows.FrameworkElement.Name%2A>.

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

Al igual que una variable, el nombre XAML de una instancia está regido por un concepto de ámbito, de manera que se puedan aplicar los nombres para que sean únicos dentro de un ámbito predecible. El marcado primario que define una página indica un ámbito de nombres de código XAML único, siendo el límite de dicho ámbito el elemento raíz de la página. Pero otros orígenes de marcado pueden interactuar con una página en tiempo de ejecución, por ejemplo, los estilos o las plantillas incluidas en los estilos, y esos orígenes tienen a menudo sus propios ámbitos de nombre XAML que no tienen por qué estar conectados necesariamente con el de la página. Para obtener más información sobre `x:Name` y los ámbitos de nombres XAML, vea <xref:System.Windows.FrameworkElement.Name%2A>, [x:Name (directiva)](../xaml-services/xname-directive.md) o [Ámbitos de nombres XAML de WPF](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

## <a name="attached-properties-and-attached-events"></a>Propiedades y eventos adjuntos

XAML incluye una característica de lenguaje que permite especificar ciertas propiedades o eventos en cualquier elemento, independientemente de si la propiedad o el evento existe en las definiciones del tipo para el elemento en el que se establece. La versión de esta característica para las propiedades se denomina propiedad adjunta y la versión para los eventos se denomina evento adjunto. Conceptualmente, las propiedades y los eventos adjuntos se pueden considerar como miembros globales que se pueden establecer en cualquier elemento o instancia de objeto XAML. En cambio, ese elemento, clase o infraestructura mayor debe admitir un almacén de propiedades de respaldo para los valores adjuntos.

Las propiedades adjuntas de código XAML se usan normalmente mediante la sintaxis de atributos. En la sintaxis de atributos, una propiedad adjunta se especifica con el formato `ownerType.propertyName`.

A primera vista, esto se parece al uso de un elemento de propiedad, pero en este caso el valor `ownerType`que se especifica es siempre un tipo distinto del elemento de objeto en el que se establece la propiedad adjunta. `ownerType` es el tipo que proporciona los métodos de descriptor de acceso que un procesador XAML necesita para poder obtener o establecer el valor de propiedad adjunto.

El escenario más común para las propiedades adjuntas es permitir a los elementos secundarios enviar un valor de propiedad a su elemento primario.

En el ejemplo siguiente se muestra la propiedad adjunta <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. La clase <xref:System.Windows.Controls.DockPanel> define los descriptores de acceso para <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> y, por tanto, es propietaria de la propiedad adjunta. La clase <xref:System.Windows.Controls.DockPanel> también incluye lógica que recorre en iteración sus elementos secundarios y comprueba específicamente en cada elemento si hay un valor establecido de <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Si se encuentra dicho valor, este se usa durante el diseño para colocar los elementos secundarios. El uso de la propiedad adjunta <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> y esta función de posicionamiento es, de hecho, el escenario que motiva a la clase <xref:System.Windows.Controls.DockPanel>.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

En WPF, la mayoría de las propiedades adjuntas también se implementan como propiedades de dependencia. Para más información, consulte la [información general sobre propiedades adjuntas](../../framework/wpf/advanced/attached-properties-overview.md).

Los eventos adjuntos usan un formato de sintaxis de atributos `ownerType.eventName` similar. Al igual que en los eventos no adjuntos, el valor del atributo para un evento adjunto en código XAML especifica el nombre del método controlador que se invoca cuando se controla el evento en el elemento. Los usos de eventos adjuntos en código XAML de WPF son menos comunes. Para obtener más información, vea [Información general sobre eventos adjuntos](../../framework/wpf/advanced/attached-events-overview.md).

## <a name="base-types-and-xaml"></a>Tipos base y XAML

De forma subyacente al código XAML de WPF y su espacio de nombres XAML existe una colección de tipos que corresponden a objetos de CLR, así como elementos de marcado para XAML. En cambio, no todas las clases se pueden asignar a elementos. Las clases abstractas, como <xref:System.Windows.Controls.Primitives.ButtonBase>, y ciertas clases base no abstractas, se usan para la herencia en el modelo de objetos de CLR. Las clases base, incluidas las abstractas, son importantes para el desarrollo de código XAML porque cada uno de los elementos de código XAML concretos hereda miembros de alguna clase base en su jerarquía. A menudo, estos miembros incluyen propiedades que se pueden establecer como atributos en el elemento o eventos que se pueden controlar. <xref:System.Windows.FrameworkElement> es la clase de interfaz de usuario base concreta de WPF en el nivel de marco de WPF. Al diseñar la interfaz de usuario, se usarán varias clases de forma, de panel, de decorador o de control, que se derivan de <xref:System.Windows.FrameworkElement>. Una clase base relacionada, <xref:System.Windows.FrameworkContentElement>, admite elementos orientados a documentos que funcionan bien para una presentación de diseño de flujo, mediante API que reflejan deliberadamente las de <xref:System.Windows.FrameworkElement>. La combinación de atributos en el nivel de elemento y un modelo de objetos de CLR proporciona un conjunto de propiedades comunes que se pueden establecer en la mayoría de los elementos XAML concretos, con independencia del tipo de elemento específico y su tipo subyacente.

## <a name="xaml-security"></a>Seguridad de XAML

XAML es un lenguaje de marcado que representa directamente la creación de instancias y la ejecución de objetos. Por consiguiente, los elementos creados en código XAML tienen la misma capacidad de interactuar con los recursos del sistema (por ejemplo, el acceso a la red y la E/S del sistema de archivos) que el código generado equivalente. El código XAML que se carga en una aplicación de plena confianza tiene el mismo acceso a los recursos del sistema que la aplicación de hospedaje.

### <a name="code-access-security-cas-in-wpf"></a>Seguridad de acceso del código (CAS) en WPF

**Esta sección solo se aplica a .NET Framework. WPF para .NET Core no es compatible con CAS. Para obtener más información, vea [Diferencias sobre la seguridad de acceso del código](../migration/differences-from-net-framework.md#code-access-security).**

WPF para .NET Framework admite la seguridad de acceso del código (CAS). Esto significa que el contenido de WPF que se ejecuta en la zona de Internet tiene permisos de ejecución reducidos. "XAML dinámico" (las páginas de código XAML no compilado interpretadas en tiempo de carga mediante un visor XAML) y XBAP normalmente se ejecutan en esta zona de Internet y usan el mismo conjunto de permisos. Pero el código XAML que se carga en una aplicación de plena confianza tiene el mismo acceso a los recursos del sistema que la aplicación de hospedaje. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../framework/wpf/wpf-partial-trust-security.md).

## <a name="loading-xaml-from-code"></a>Carga de XAML desde código

XAML se puede usar para definir la totalidad de la interfaz de usuario, pero a veces también es conveniente definir solo una parte de dicha interfaz en código XAML. Esta función se podría usar para habilitar una personalización parcial, para el almacenamiento local de información, para proporcionar un objeto comercial mediante código XAML o para diversos escenarios posibles. La clave para estos escenarios es la clase <xref:System.Windows.Markup.XamlReader> y su método <xref:System.Windows.Markup.XamlReader.Load%2A>. La entrada es un archivo XAML y la salida es un objeto que representa la totalidad del árbol de objetos en tiempo de ejecución que se ha creado a partir de ese marcado. Después, se puede insertar el objeto como una propiedad de otro objeto que ya existe en la aplicación. Siempre que la propiedad sea una propiedad adecuada en el modelo de contenido que tiene funciones de presentación y que notifica al motor de ejecución que se ha agregado el nuevo contenido a la aplicación, se puede modificar con facilidad el contenido de una aplicación en ejecución si se carga código XAML. Para .NET Framework, esta función normalmente solo está disponible en las aplicaciones de plena confianza, debido a las implicaciones de seguridad obvias de la carga de archivos en aplicaciones mientras se ejecutan.

## <a name="see-also"></a>Vea también

- [Detalles de la sintaxis XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [Clases XAML y personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Características del lenguaje del espacio de nombres de XAML (x:)](../xaml-services/namespace-language-features.md)
- [Extensiones XAML de WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [Información general sobre elementos base](../../framework/wpf/advanced/base-elements-overview.md)
- [Árboles en WPF](../../framework/wpf/advanced/trees-in-wpf.md)
