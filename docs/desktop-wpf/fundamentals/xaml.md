---
title: Información general sobre XAML
description: Obtén información sobre cómo Windows Presentation Foundation (WPF) estructura e implementa el lenguaje XAML para .NET Core.
author: thraka
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
ms.openlocfilehash: b0a9357b623fbde08731a5b1ddb8fee3a93824c2
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "81433005"
---
# <a name="xaml-overview-in-wpf"></a>Descripción general de XAML en WPFWPF

En este artículo se describen las características del lenguaje XAML y se muestra cómo puede usar XAML para escribir aplicaciones de Windows Presentation Foundation (WPF). En este artículo se describe específicamente XAML tal como lo implementa WPFWPF. XAML en sí es un concepto de lenguaje más grande que WPFWPF.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>Qué es XAML

XAML es un lenguaje declarativo de marcado. Como se aplica al modelo de programación de .NET Core, XAML simplifica la creación de una interfaz de usuario para una aplicación de .NET Core. Puede crear elementos de interfaz de usuario visibles en el marcado XAML declarativo y, a continuación, separar la definición de interfaz de usuario de la lógica en tiempo de ejecución mediante el uso de archivos de código subyacente que se unen al marcado a través de definiciones de clase parciales. XAML representa directamente la creación de instancias de objetos en un conjunto concreto de tipos de respaldo definidos en ensamblados. Esto no es lo que sucede con la mayoría de lenguajes de marcado, que normalmente se interpretan sin esa relación directa con un sistema de tipos de respaldo. XAML permite un flujo de trabajo donde partes independientes pueden trabajar en la interfaz de usuario y la lógica de una aplicación, utilizando herramientas potencialmente diferentes.

Cuando se representan como texto, los archivos XAML son archivos XML que generalmente tienen la extensión `.xaml`. Los archivos se pueden codificar con cualquier codificación XML, pero lo habitual es la codificación UTF-8.

En el ejemplo siguiente se muestra cómo crear un botón como parte de una interfaz de usuario. Este ejemplo está pensado para darle un sabor de cómo XAML representa metáforas de programación de interfaz de usuario comunes (no es un ejemplo completo).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>Sintaxis XAML en breve

En las secciones siguientes se explican las formas básicas de la sintaxis XAML y se proporciona un breve ejemplo de marcado. Estas secciones no están pensadas para proporcionar información completa sobre cada sintaxis, por ejemplo, cómo se representan en el sistema de tipos de respaldo. Para obtener más información acerca de los detalles de la sintaxis XAML, vea [Sintaxis XAML en detalle](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

Gran parte del material en las siguientes secciones será elemental para usted si tiene familiaridad previa con el lenguaje XML. Esta es una consecuencia de uno de los principios de diseño básicos de XAML. El lenguaje XAML define conceptos propios, pero estos conceptos funcionan dentro del lenguaje XML y el formulario de marcado.

### <a name="xaml-object-elements"></a>Elementos de objeto XAML

Normalmente, un elemento de objeto declara una instancia de un tipo. Ese tipo se define en los ensamblados a los que hace referencia la tecnología que usa XAML como lenguaje.

La sintaxis del elemento de objeto siempre se inicia con un corchete angular de apertura (`<`). Este va seguido del nombre del tipo donde quiere crear una instancia. (El nombre puede incluir un prefijo, un concepto que se explicará más adelante.) Después de esto, puede declarar atributos en el elemento de objeto. Para completar la etiqueta de elemento de`>`objeto, termine con un corchete angular de cierre ( ). En su lugar, puede utilizar un formulario de cierre automático que no tenga ningún contenido,`/>`completando la etiqueta con una barra diagonal y un corchete angular de cierre en sucesión ( ). Por ejemplo, vuelva a examinar el fragmento de código de marcado mostrado anteriormente.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

Esto especifica dos elementos de objeto: `<StackPanel>` (con contenido y una etiqueta de cierre después) y `<Button .../>` (el formulario de autocierre, con varios atributos). Los `StackPanel` elementos `Button` de objeto y cada asignación al nombre de una clase definida por WPFWPF y forma parte de los ensamblados WPFWPF. Cuando se especifica una etiqueta de elemento de objeto, se crea una instrucción para el procesamiento XAML para crear una nueva instancia del tipo subyacente. Cada instancia se crea llamando al constructor sin parámetros del tipo subyacente al analizar y cargar el XAML.

### <a name="attribute-syntax-properties"></a>Sintaxis de atributo (propiedades)

Las propiedades de un objeto se pueden expresar a menudo como atributos del elemento de objeto. La sintaxis de atributo nombra la propiedad de objeto que se está estableciendo, seguida del operador de asignación (-). El valor de un atributo siempre se especifica como una cadena incluida entre comillas.

La sintaxis de atributo es la sintaxis de establecimiento de propiedades más optimizada y será la más intuitiva para los desarrolladores que han usado lenguajes de marcado anteriormente. Por ejemplo, el marcado siguiente crea un botón que tiene texto rojo y un fondo azul, además de mostrar texto especificado como `Content`.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>Sintaxis de elemento de propiedad

En algunas propiedades de un elemento de objeto, no es posible usar la sintaxis de atributo, ya que el objeto o la información necesaria para proporcionar el valor de propiedad no se puede expresar correctamente dentro de las comillas y restricciones de cadena de la sintaxis de atributo. En estos casos, se puede usar otra sintaxis conocida como sintaxis de elementos de propiedad.

La sintaxis de la `<TypeName.PropertyName>`etiqueta de inicio del elemento de propiedad es . Por lo general, el contenido de esa etiqueta es un elemento de objeto del tipo que la propiedad toma como su valor. Después de especificar el contenido, debe cerrar el elemento de propiedad con una etiqueta final. La sintaxis de `</TypeName.PropertyName>`la etiqueta final es .

Si es posible usar una sintaxis de atributo, su uso es generalmente más conveniente, ya que habilita un marcado más compacto, pero suele ser una cuestión de estilo, no una limitación técnica. En el ejemplo siguiente se muestra cómo se establecen las mismas propiedades que en el ejemplo anterior de sintaxis de atributo, pero ahora usando la sintaxis de elementos de propiedad para todas las propiedades de `Button`.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>Sintaxis de colección

El lenguaje XAML incluye algunas optimizaciones que generan un marcado más legible. Una de estas optimizaciones consiste en que si una propiedad determinada toma un tipo de colección, entonces los elementos que se declaran en el marcado como elementos secundarios dentro del valor de esa propiedad se convierten en parte de la colección. En este caso, una colección de elementos de objeto secundarios es el valor que se establece para la propiedad de la colección.

En el ejemplo siguiente se muestra <xref:System.Windows.Media.GradientBrush.GradientStops%2A> la sintaxis de la colección para establecer los valores de la propiedad.

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

XAML especifica una característica de lenguaje mediante la que una clase puede designar exactamente una de sus propiedades para que sea la propiedad de _contenido_ XAML. Los elementos secundarios de ese elemento de objeto se usan para establecer el valor de esa propiedad de contenido. Es decir, únicamente para la propiedad de contenido, puede omitir un elemento de propiedad cuando se establece esa propiedad en marcado XAML y genera una metáfora de elemento primario/secundario más visible en el marcado.

Por ejemplo, <xref:System.Windows.Controls.Border> especifica _una_ propiedad content de <xref:System.Windows.Controls.Decorator.Child%2A>. Los dos <xref:System.Windows.Controls.Border> elementos siguientes se tratan de forma idéntica. El primero se aprovecha de la sintaxis de la propiedad de contenido y omite el elemento de propiedad `Border.Child`. El segundo muestra `Border.Child` explícitamente.

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

Como regla del lenguaje XAML, el valor de una propiedad de contenido de XAML se debe proporcionar exclusivamente antes o después de cualquier otro elemento de propiedad en ese elemento de objeto. Por ejemplo, el siguiente marcado no se compila.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

Para obtener más información acerca de los detalles de la sintaxis XAML, vea [Sintaxis XAML en detalle](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

### <a name="text-content"></a>Contenido de texto

Un pequeño número de elementos de código XAML puede procesar directamente el texto como su contenido. Para habilitar esto, debe cumplirse una de estas situaciones:

- La clase debe declarar una propiedad content y esa propiedad content debe ser <xref:System.Object>de un tipo asignable a una cadena (el tipo podría ser ). Por ejemplo, <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ContentControl.Content%2A> cualquier uso como su <xref:System.Object>propiedad content y es type <xref:System.Windows.Controls.ContentControl> , <xref:System.Windows.Controls.Button>y `<Button>Hello</Button>`esto admite el siguiente uso en un: .

- El tipo debe declarar un convertidor de tipos, en cuyo caso el contenido de texto se usa como texto de inicialización para ese convertidor de tipos. Por ejemplo, `<Brush>Blue</Brush>` convierte el `Blue` valor de contenido en un pincel. Este caso es menos común en la práctica.

- El tipo debe ser una primitiva conocida del lenguaje XAML.

### <a name="content-properties-and-collection-syntax-combined"></a>Propiedades de contenido y sintaxis de colección combinadas

Considere este ejemplo.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

Aquí, <xref:System.Windows.Controls.Button> cada uno es <xref:System.Windows.Controls.StackPanel>un elemento secundario de . Este es un marcado optimizado e intuitivo que omite dos etiquetas por dos razones diferentes.

- **Omitido StackPanel.Children elemento** <xref:System.Windows.Controls.StackPanel> de <xref:System.Windows.Controls.Panel>propiedad: deriva de . <xref:System.Windows.Controls.Panel>define <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> como su propiedad de contenido XAML.

- Elemento de **objeto UIElementCollection omitido:** La <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> propiedad toma <xref:System.Windows.Controls.UIElementCollection>el tipo <xref:System.Collections.IList>, que implementa . La etiqueta de elemento de la colección se puede omitir, <xref:System.Collections.IList>en función de las reglas XAML para procesar colecciones como . (En este <xref:System.Windows.Controls.UIElementCollection> caso, en realidad no se puede crear una instancia porque <xref:System.Windows.Controls.UIElementCollection> no expone un constructor sin parámetros y es por eso que el elemento de objeto se muestra comentado).

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

### <a name="attribute-syntax-events"></a>Sintaxis de atributo (eventos)

La sintaxis de atributos también se puede usar para los miembros que son eventos en lugar de propiedades. En este caso, el nombre del atributo es el nombre del evento. En la implementación WPF de eventos para XAML, el valor del atributo es el nombre de un controlador que implementa el delegado de ese evento. Por ejemplo, el marcado siguiente asigna <xref:System.Windows.Controls.Primitives.ButtonBase.Click> un <xref:System.Windows.Controls.Button> controlador para el evento a un creado en el marcado:

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

En WPF, los eventos y el código XAML son más complejos que este ejemplo de la sintaxis de atributos. Por ejemplo, podría preguntarse qué representa el elemento `ClickHandler` al que se hace referencia aquí y cómo se define. Esto se explicará en la próxima sección [de eventos y código subyacente XAML](#events-and-xaml-code-behind) de este artículo.

## <a name="case-and-white-space-in-xaml"></a>Caso y espacio en blanco en XAML

En general, XAML distingue mayúsculas de minúsculas. Para resolver tipos de respaldo, XAML de WPF distingue mayúsculas de minúsculas por las mismas reglas que CLR distingue mayúsculas de minúsculas. Los elementos de objeto, los elementos de propiedad y los nombres de atributo se deben especificar usando la grafía que distinga mayúsculas de minúsculas cuando se comparan por nombre con el tipo subyacente en el ensamblado, o con un miembro de un tipo. Las palabras clave y primitivas del lenguaje XAML también distinguen mayúsculas de minúsculas. Los valores no siempre distinguen mayúsculas de minúsculas. La distinción entre mayúsculas y minúsculas para los valores dependerá del comportamiento del convertidor de tipos asociado a la propiedad que toma el valor o del tipo de valor de propiedad. Por ejemplo, las <xref:System.Boolean> propiedades que `true` toman `True` el tipo pueden tomar uno o como valores equivalentes, pero solo porque la conversión de tipo de analizador XAML de WPF nativo para cadena ya <xref:System.Boolean> permite estos como equivalentes.

Los procesadores y serializadores XAML de WPF omitirán o quitarán todos los espacios en blanco no significativos y normalizarán cualquier espacio en blanco significativo. Esto es coherente con las recomendaciones de comportamiento de espacio en blanco predeterminadas de la especificación XAML. Este comportamiento solo es consecuencia cuando se especifican cadenas dentro de las propiedades de contenido XAML. En términos más simples, XAML convierte caracteres de espacio, salto de línea y tabulación en espacios y, a continuación, conserva un espacio si se encuentra en cualquiera de los extremos de una cadena contigua. La explicación completa del control de espacio en blanco XAML no se trata en este artículo. Para obtener más información, vea Procesamiento de [espacio en blanco en XAML](../xaml-services/white-space-processing.md).

## <a name="markup-extensions"></a>Extensiones de marcado

Las extensiones de marcado son un concepto del lenguaje XAML. Cuando se usan para proporcionar el valor de una sintaxis de atributos, las llaves (`{` y `}`) indican el uso de una extensión de marcado. Este uso hace que el procesamiento XAML se aparte del tratamiento general de valores de atributo como una cadena literal o un valor directamente convertible en cadena.

Las extensiones de marcado más [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md)comunes utilizadas en la programación [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md)de aplicaciones WPFWPF son , que se usan para expresiones de enlace de datos y las referencias de recursos y . Al usar las extensiones de marcado, puede usar la sintaxis de atributos para proporcionar valores para las propiedades aunque esa propiedad no admita una sintaxis de atributos en general. Las extensiones de marcado suelen utilizar tipos de expresión intermedios para habilitar características como aplazar valores o hacer referencia a otros objetos que solo están presentes en tiempo de ejecución.

Por ejemplo, el siguiente marcado <xref:System.Windows.FrameworkElement.Style%2A> establece el valor de la propiedad mediante la sintaxis de atributo. La <xref:System.Windows.FrameworkElement.Style%2A> propiedad toma una <xref:System.Windows.Style> instancia de la clase, que de forma predeterminada no se pudo crear una instancia mediante una cadena de sintaxis de atributo. Pero en este caso, el atributo `StaticResource`hace referencia a una extensión de marcado determinada, . Cuando se procesa dicha extensión de marcado, devuelve una referencia a un estilo del que ya se han creado instancias como un recurso con clave en un diccionario de recursos.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

Para obtener una lista de referencias de todas las extensiones de marcado para XAML implementadas específicamente en WPF, vea [Extensiones XAML de WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md). Para obtener una lista de referencia de las extensiones de marcado definidas por System.Xaml y están más ampliamente disponibles para las implementaciones XAML de .NET Core, vea Espacio de [nombres XAML (x:) Características del idioma](../xaml-services/namespace-language-features.md). Para obtener más información sobre los conceptos de la extensión de marcado, vea [Extensiones de marcado y XAML de WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="type-converters"></a>Convertidores de tipo

En la sección [Resumen de sintaxis de XAML](#xaml-syntax-in-brief), se ha mencionado que el valor de atributo debe poder establecerlo una cadena. El control básico y nativo de cómo se convierten las <xref:System.String> cadenas en otros tipos de objeto o <xref:System.DateTime> <xref:System.Uri>valores primitivos se basa en el propio tipo, además del procesamiento nativo para determinados tipos, como o . Pero muchos tipos de WPFWPF o miembros de esos tipos extienden el comportamiento de procesamiento de atributos de cadena básico de tal manera que las instancias de tipos de objeto más complejos se pueden especificar como cadenas y atributos.

La <xref:System.Windows.Thickness> estructura es un ejemplo de un tipo que tiene una conversión de tipos habilitada para usos XAML. <xref:System.Windows.Thickness>indica mediciones dentro de un rectángulo anidado y se <xref:System.Windows.FrameworkElement.Margin%2A>utiliza como el valor de propiedades como . Al colocar un <xref:System.Windows.Thickness>convertidor de tipos <xref:System.Windows.Thickness> en , todas las propiedades que usan a son más fáciles de especificar en XAML porque se pueden especificar como atributos. En el ejemplo siguiente se utiliza una conversión <xref:System.Windows.FrameworkElement.Margin%2A>de tipos y una sintaxis de atributo para proporcionar un valor para:

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

El ejemplo de sintaxis de atributo anterior es equivalente <xref:System.Windows.FrameworkElement.Margin%2A> al siguiente ejemplo de <xref:System.Windows.Thickness> sintaxis más detallado, donde se establece en su lugar a través de la sintaxis de elemento de propiedad que contiene un elemento de objeto. Las cuatro propiedades <xref:System.Windows.Thickness> clave de se establecen como atributos en la nueva instancia:

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> También hay un número limitado de objetos donde la conversión de tipos es la única forma pública de establecer una propiedad en ese tipo sin implicar una subclase, porque el propio tipo no tiene un constructor sin parámetros. Un ejemplo es <xref:System.Windows.Input.Cursor>.

Para obtener más información sobre la conversión de tipos, vea [TypeConverters y XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

## <a name="xaml-root-elements-and-xaml-namespaces"></a>Elementos raíz XAML y espacios de nombres XAML

Un archivo XAML debe tener solo un elemento raíz, para que sea un archivo XML bien formado y un archivo XAML válido. Para escenarios típicos de WPFWPF, use un elemento raíz que tenga <xref:System.Windows.Window> <xref:System.Windows.Controls.Page> un significado <xref:System.Windows.ResourceDictionary> prominente en el <xref:System.Windows.Application> modelo de aplicación WPF (por ejemplo, o para una página, para un diccionario externo o para la definición de la aplicación). En el ejemplo siguiente se muestra el elemento raíz de un <xref:System.Windows.Controls.Page>archivo XAML típico para una página WPFWPF, con el elemento raíz de .

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

El elemento raíz también contiene los atributos `xmlns` y `xmlns:x`. Estos atributos indican a un procesador XAML los espacios de nombres XAML que contienen las definiciones de tipo de los tipos de respaldo a los que el marcado hará referencia como elementos. El atributo `xmlns` indica específicamente el espacio de nombres XAML predeterminado. Dentro del espacio de nombres XAML predeterminado, los elementos de objeto en el marcado se pueden especificar sin un prefijo. Para la mayoría de los escenarios de aplicación WPFWPF y para casi todos los ejemplos que `http://schemas.microsoft.com/winfx/2006/xaml/presentation`se proporcionan en las secciones WPF del SDK, el espacio de nombres XAML predeterminado se asigna al espacio de nombres WPF. El atributo `xmlns:x` indica un espacio de nombres XAML adicional, que asigna el espacio de nombres del lenguaje XAML `http://schemas.microsoft.com/winfx/2006/xaml`.

Este uso de `xmlns` para definir un ámbito para el uso y asignación de un ámbito de nombres es coherente con la especificación XML 1.0. Los ámbitos de nombres de código XAML solo se diferencian de los ámbitos de nombres de XML en que un ámbito de nombres de código XAML también implica a la forma en que los tipos respaldan los elementos del ámbito de nombres cuando se trata de la resolución de tipos y del análisis del código XAML.

Los `xmlns` atributos solo son estrictamente necesarios en el elemento raíz de cada archivo XAML. Las definiciones de `xmlns` se aplicarán a todos los elementos descendientes del elemento raíz (una vez más, este comportamiento es coherente con la especificación XML 1.0 para `xmlns`). También se permiten atributos `xmlns` en otros elementos bajo la raíz, y se aplican a cualquier elemento descendiente del elemento de definición. En cambio, una definición o redefinición frecuente de los espacios de nombres XAML puede dar lugar a un estilo de marcado XAML que resulte difícil de leer.

La implementación de WPFWPF de su procesador XAML incluye una infraestructura que tiene conocimiento de los ensamblados principales de WPFWPF. Se sabe que los ensamblados principales de WPFWPF contienen los tipos que admiten las asignaciones de WPFWPF al espacio de nombres XAML predeterminado. Esto se habilita a través de la configuración que forma parte de su archivo de compilación de proyecto y los sistemas de compilación y proyectos de WPF. Por lo tanto, declarar el `xmlns` espacio de nombres XAML predeterminado como el valor predeterminado es todo lo que es necesario para hacer referencia a los elementos XAML que proceden de wpfWPF ensamblados.

### <a name="the-x-prefix"></a>El prefijo x:

En el ejemplo de elemento raíz anterior, el prefijo `x:` se ha usado para asignar el espacio de nombres XAML `http://schemas.microsoft.com/winfx/2006/xaml`, que es el espacio de nombres XAML dedicado que admite las construcciones de lenguaje XAML. Este `x:` prefijo se usa para asignar este espacio de nombres XAML en las plantillas para proyectos, en ejemplos y en la documentación de este SDK. El espacio de nombres XAML para el lenguaje XAML contiene varias construcciones de programación que usará con frecuencia en el XAML. A continuación se muestra una lista de las construcciones de programación del prefijo `x:` más comunes que usará:

- [x:Key](../xaml-services/xkey-directive.md): Establece una clave única <xref:System.Windows.ResourceDictionary> para cada recurso en un (o conceptos de diccionario similares en otros marcos). `x:Key`probablemente representará el 90 `x:` por ciento de los usos que verá en el marcado típico de la aplicación WPFWPF.

- [x:Class](../xaml-services/xclass-directive.md): especifica el espacio de nombres CLR y el nombre de clase para la clase que proporciona código subyacente para una página XAML. Debe disponer de esta clase para admitir el código subyacente por el modelo de programación WPF; por esto casi siempre verá `x:` asignado, aunque no haya ningún recurso.

- [x:Name](../xaml-services/xname-directive.md): especifica un nombre de objeto en tiempo de ejecución para la instancia que existe en el código en tiempo de ejecución una vez procesado un elemento de objeto. En general, usará frecuentemente una propiedad equivalente definida por WPF para [x:Name](../xaml-services/xname-directive.md). Estas propiedades se asignan específicamente a una propiedad de respaldo de CLR y, por lo tanto, son más convenientes para la programación de aplicaciones, donde se usa con frecuencia código en tiempo de ejecución para buscar los elementos con nombre de XAML inicializado. El material de <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>such property es . Puede seguir usando [x:Name](../xaml-services/xname-directive.md) cuando la <xref:System.Windows.FrameworkElement.Name%2A> propiedad de nivel de marco de WPF equivalente no se admite en un tipo determinado. Esto sucede en ciertos escenarios de animación.

- [x:Static](../xaml-services/xstatic-markup-extension.md): habilita una referencia que obtiene un valor estático que, de lo contrario, no sería una propiedad compatible con XAML.

- [x:Tipo](../xaml-services/xtype-markup-extension.md): Construye <xref:System.Type> una referencia basada en un nombre de tipo. Esto se utiliza para <xref:System.Type>especificar atributos que toman , como <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>,<xref:System.Type> aunque con frecuencia la propiedad tiene la conversión de cadena a cuna nativa de tal manera que el uso de la extensión de marcado [x:Type](../xaml-services/xtype-markup-extension.md) es opcional.

Hay construcciones de programación adicionales en el prefijo o espacio de nombres XAML `x:` que no son tan habituales. Para obtener información detallada, vea [Características de lenguaje (x:) de espacios de nombres XAML](../xaml-services/namespace-language-features.md).

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Prefijos personalizados y tipos personalizados en XAML

Para sus propios ensamblados personalizados, o para ensamblados fuera del núcleo WPF de **PresentationCore**, `xmlns` **PresentationFramework** y **WindowsBase**, puede especificar el ensamblado como parte de una asignación personalizada. Después, puede hacer referencia a los tipos de ese ensamblado en su código XAML, siempre que su tipo esté implementado correctamente para admitir los usos de código XAML que intenta.

A continuación se muestra un ejemplo básico de cómo funcionan los prefijos personalizados en el marcado XAML. El `custom` prefijo se define en la etiqueta de elemento raíz y se asigna a un ensamblado específico que está empaquetado y disponible con la aplicación. Este ensamblado contiene un tipo `NumericUpDown`, que se implementa para admitir el uso XAML general, además de usar una herencia de clases que permite su inserción en este punto concreto en un modelo de contenido de código XAML de WPF. Se declara una instancia de este control `NumericUpDown` como un elemento de objeto, usando el prefijo para que un analizador de código XAML sepa qué espacio de nombres XAML contiene el tipo y, por consiguiente, dónde está el ensamblado de respaldo que contiene la definición de tipo.

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

Para obtener más información sobre cómo se relacionan los espacios de nombres XML y los espacios de nombres de código en ensamblados, vea [Espacios de nombres XAML y Asignación](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF .

## <a name="events-and-xaml-code-behind"></a>Eventos y código subyacente XAML

La mayoría de las aplicaciones WPFWPF constan de marcado XAML y código subyacente. Dentro de un proyecto, el `.xaml` XAML se escribe como un archivo y se usa un lenguaje CLR como Microsoft Visual Basic o C- para escribir un archivo de código subyacente. Cuando se compila un archivo XAML como parte de los modelos de aplicaciones y programación de WPF, la ubicación del archivo de código subyacente XAML para cada archivo XAML se identifica especificando un espacio de nombres y una clase como el atributo `x:Class` del elemento raíz de XAML.

En los ejemplos presentados hasta ahora se incluían varios botones, pero ninguno de ellos tenía todavía ningún comportamiento lógico asociado. El mecanismo principal de nivel de aplicación para agregar un comportamiento para un elemento de objeto es usar un evento existente de la clase de elemento y escribir un controlador específico para ese evento que se invoca cuando se genera ese evento en tiempo de ejecución. El nombre del evento y el nombre del controlador que se van a usar se especifican en el marcado, mientras que el código que implementa el controlador se define en el código subyacente.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

Tenga en cuenta que el archivo de código subyacente usa el espacio de nombres CLR `ExampleNamespace` y declara `ExamplePage` como una clase parcial dentro de dicho espacio de nombres. Esto es similar al valor de atributo `x:Class` de `ExampleNamespace`.`ExamplePage` que se ha proporcionado en la raíz del marcado. El compilador de marcado WPF creará una clase parcial para cualquier archivo XAML compilado, al derivar una clase del tipo de elemento raíz. Cuando se proporciona código subyacente que también define la misma clase parcial, el código resultante se combina dentro del mismo espacio de nombres y clase de la aplicación compilada.

Para obtener más información acerca de los requisitos para la programación de código subyacente en WPFWPF, vea código subyacente, controlador de eventos y requisitos de [clase parcial en WPFWPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf).

Si no quiere crear un archivo de código subyacente independiente, también puede insertar el código dentro de un archivo XAML. En cambio, el código insertado es una técnica menos versátil que tiene importantes limitaciones. Para obtener más información, vea [Código subyacente y XAML en WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

### <a name="routed-events"></a>Eventos enrutados

Una característica de evento determinada que es fundamental para WPFWPF es un evento enrutado. Los eventos enrutados permiten a un elemento controlar un evento generado por otro elemento diferente, siempre que dichos elementos estén relacionados entre sí a través de un árbol. Al especificar el control de eventos con un atributo XAML, se puede escuchar y controlar el evento enrutado en cualquier elemento, incluidos los elementos que no contienen ese evento concreto en la tabla de miembros de clase. Esto se consigue calificando el atributo de nombre de evento con el nombre de la clase propietaria. Por ejemplo, `StackPanel` el elemento `StackPanel`  /  `Button` primario del ejemplo en curso podría <xref:System.Windows.Controls.Primitives.ButtonBase.Click> registrar un controlador `Button.Click` para `StackPanel` el evento del botón de elemento secundario especificando el atributo en el elemento de objeto, con el nombre del controlador como valor de atributo. Para obtener más información, consulte [Información general sobre eventos enrutados](../../framework/wpf/advanced/routed-events-overview.md).

## <a name="xaml-named-elements"></a>Elementos con nombre XAML

De manera predeterminada, la instancia de objeto que se crea en un gráfico de objetos al procesar un elemento de objeto XAML no posee un identificador único o una referencia de objeto. Por el contrario, si llama a un constructor en el código, casi siempre usa el resultado del constructor para establecer una variable en la instancia creada, de manera que pueda hacer referencia a dicha instancia posteriormente en el código. Para proporcionar acceso normalizado a los objetos creados mediante una definición de marcado, XAML define el [atributo x:Name](../xaml-services/xname-directive.md). Es posible establecer el valor del atributo `x:Name` en cualquier elemento de objeto. En el código subyacente, el identificador elegido es equivalente a una variable de instancia que hace referencia a la instancia creada. En todos los aspectos, los elementos con nombre funcionan como si fueran instancias de objeto (el nombre hace referencia a esa instancia) y el código subyacente puede hacer referencia a los elementos con nombre para controlar las interacciones en tiempo de ejecución dentro de la aplicación. Esta conexión entre instancias y variables se realiza mediante el compilador de marcado <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> XAML de WPF y, más específicamente, implica características y patrones como ese no se tratarán en detalle en este artículo.

Los elementos XAML de <xref:System.Windows.FrameworkElement.Name%2A> nivel de marco de `x:Name` WPF HEREdan una propiedad, que es equivalente al atributo definido XAML. Otras clases también proporcionan equivalentes en el nivel de propiedad para `x:Name`, que en general también suele definirse como una propiedad `Name`. En general, si no puede localizar una propiedad `Name` en la tabla de miembros del elemento/tipo elegido, use `x:Name` en su lugar. Los `x:Name` valores proporcionarán un identificador a un elemento XAML que se puede usar en tiempo <xref:System.Windows.FrameworkElement.FindName%2A>de ejecución, ya sea por subsistemas específicos o por métodos de utilidad como .

En el <xref:System.Windows.FrameworkElement.Name%2A> ejemplo <xref:System.Windows.Controls.StackPanel> siguiente se establece en un elemento. A continuación, un <xref:System.Windows.Controls.Button> controlador <xref:System.Windows.Controls.StackPanel> en <xref:System.Windows.Controls.StackPanel> un dentro `buttonContainer` de <xref:System.Windows.FrameworkElement.Name%2A>que hace referencia a través de su referencia de instancia como establecido por .

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

Al igual que una variable, el nombre XAML de una instancia está regido por un concepto de ámbito, de manera que se puedan aplicar los nombres para que sean únicos dentro de un ámbito predecible. El marcado primario que define una página indica un ámbito de nombres de código XAML único, siendo el límite de dicho ámbito el elemento raíz de la página. Sin embargo, otros orígenes de marcado pueden interactuar con una página en tiempo de ejecución, como estilos o plantillas dentro de estilos, y estos orígenes de marcado a menudo tienen sus propios ámbitos de nombres XAML que no se conectan necesariamente con el ámbito de nombres XAML de la página. Para obtener `x:Name` más información sobre los <xref:System.Windows.FrameworkElement.Name%2A>ámbitos de nombres XAML, vea , [x:Name Directive](../xaml-services/xname-directive.md)o [WPF XAML Namescopes](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

## <a name="attached-properties-and-attached-events"></a>Propiedades adjuntas y eventos adjuntos

XAML incluye una característica de lenguaje que permite especificar ciertas propiedades o eventos en cualquier elemento, independientemente de si la propiedad o el evento existe en las definiciones del tipo para el elemento en el que se establece. La versión de esta característica para las propiedades se denomina propiedad adjunta y la versión para los eventos se denomina evento adjunto. Conceptualmente, las propiedades y los eventos adjuntos se pueden considerar como miembros globales que se pueden establecer en cualquier elemento o instancia de objeto XAML. En cambio, ese elemento, clase o infraestructura mayor debe admitir un almacén de propiedades de respaldo para los valores adjuntos.

Las propiedades adjuntas de código XAML se usan normalmente mediante la sintaxis de atributos. En la sintaxis de atributo, `ownerType.propertyName`especifique una propiedad adjunta en el formulario .

Superficialmente, esto se asemeja a un uso `ownerType` de elemento de propiedad, pero en este caso el especificar siempre es un tipo diferente que el elemento de objeto donde se establece la propiedad adjunta. `ownerType`es el tipo que proporciona los métodos de descriptor de acceso que requiere un procesador XAML para obtener o establecer el valor de propiedad adjunta.

El escenario más común para las propiedades adjuntas es permitir a los elementos secundarios enviar un valor de propiedad a su elemento primario.

En el ejemplo <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> siguiente se muestra la propiedad adjunta. La <xref:System.Windows.Controls.DockPanel> clase define los <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> descriptores de acceso y, por lo tanto, es propietaria de la propiedad adjunta. La <xref:System.Windows.Controls.DockPanel> clase también incluye lógica que recorre en iteración sus elementos <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>secundarios y comprueba específicamente cada elemento para un valor establecido de . Si se encuentra dicho valor, este se usa durante el diseño para colocar los elementos secundarios. El uso <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> de la propiedad adjunta y esta capacidad de <xref:System.Windows.Controls.DockPanel> posicionamiento es, de hecho, el escenario motivador para la clase.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

En WPFWPF, la mayoría o todas las propiedades adjuntas también se implementan como propiedades de dependencia. Para más información, consulte la [información general sobre propiedades adjuntas](../../framework/wpf/advanced/attached-properties-overview.md).

Los eventos adjuntos utilizan una forma similar `ownerType.eventName` de sintaxis de atributo. Al igual que en los eventos no adjuntos, el valor del atributo para un evento adjunto en código XAML especifica el nombre del método controlador que se invoca cuando se controla el evento en el elemento. Los usos de eventos adjuntos en código XAML de WPF son menos comunes. Para obtener más información, vea [Información general sobre eventos adjuntos](../../framework/wpf/advanced/attached-events-overview.md).

## <a name="base-types-and-xaml"></a>Tipos base y XAML

El XAML de WPF subyacente y su espacio de nombres XAML es una colección de tipos que corresponden a objetos CLR además de elementos de marcado para XAML. En cambio, no todas las clases se pueden asignar a elementos. Las clases <xref:System.Windows.Controls.Primitives.ButtonBase>abstractas, como , y ciertas clases base no abstractas, se usan para la herencia en el modelo de objetos CLR. Las clases base, incluidas las abstractas, son importantes para el desarrollo de código XAML porque cada uno de los elementos de código XAML concretos hereda miembros de alguna clase base en su jerarquía. A menudo, estos miembros incluyen propiedades que se pueden establecer como atributos en el elemento o eventos que se pueden controlar. <xref:System.Windows.FrameworkElement>es la clase de interfaz de usuario base concreta de WPFWPF en el nivel de marco de WPFWPF. Al diseñar la interfaz de usuario, usará varias clases de forma, <xref:System.Windows.FrameworkElement>panel, decorador o control, que se derivan de . Una clase base <xref:System.Windows.FrameworkContentElement>relacionada, , admite elementos orientados a documentos que funcionan bien para <xref:System.Windows.FrameworkElement>una presentación de diseño de flujo, utilizando API que reflejan deliberadamente las API en . La combinación de atributos en el nivel de elemento y un modelo de objetos CLR proporciona un conjunto de propiedades comunes que se pueden establecer en la mayoría de los elementos XAML concretos, independientemente del elemento XAML específico y su tipo subyacente.

## <a name="xaml-security"></a>Seguridad XAML

XAML es un lenguaje de marcado que representa directamente la creación de instancias y la ejecución de objetos. Por consiguiente, los elementos creados en código XAML tienen la misma capacidad de interactuar con los recursos del sistema (por ejemplo, el acceso a la red y la E/S del sistema de archivos) que el código generado equivalente. XAML cargado en una aplicación de plena confianza tiene el mismo acceso a los recursos del sistema que la aplicación de hospedaje.

### <a name="code-access-security-cas-in-wpf"></a>Seguridad de acceso de código (CAS) en WPFWPF

**Esta sección solo se aplica a .NET Framework. WPF para .NET Core no admite CAS. Para obtener más información, consulte [Diferencias](../migration/differences-from-net-framework.md#code-access-security)de seguridad de acceso de código .**

WPF para .NET Framework admite la seguridad de acceso de código (CAS). Esto significa que el contenido de WPFWPF que se ejecuta en la zona de Internet ha reducido los permisos de ejecución. "Xaml suelto" (páginas de XAML no compilado interpretadas en tiempo de carga por un visor XAML) y XBAP normalmente se ejecutan en esta zona de Internet y usan el mismo conjunto de permisos. Sin embargo, XAML cargado en una aplicación de plena confianza tiene el mismo acceso a los recursos del sistema que la aplicación de hospedaje. Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../framework/wpf/wpf-partial-trust-security.md).

## <a name="loading-xaml-from-code"></a>Carga de XAML desde el código

XAML se puede usar para definir la totalidad de la interfaz de usuario, pero a veces también es conveniente definir solo una parte de dicha interfaz en código XAML. Esta función se podría usar para habilitar una personalización parcial, para el almacenamiento local de información, para proporcionar un objeto comercial mediante código XAML o para diversos escenarios posibles. La clave de estos <xref:System.Windows.Markup.XamlReader> escenarios <xref:System.Windows.Markup.XamlReader.Load%2A> es la clase y su método. La entrada es un archivo XAML y la salida es un objeto que representa la totalidad del árbol de objetos en tiempo de ejecución que se ha creado a partir de ese marcado. A continuación, puede insertar el objeto para que sea una propiedad de otro objeto que ya existe en la aplicación. Siempre que la propiedad sea una propiedad adecuada en el modelo de contenido que tenga capacidades de presentación eventuales y que notifique al motor de ejecución que se ha agregado contenido nuevo a la aplicación, puede modificar fácilmente el contenido de una aplicación en ejecución cargando en XAML. Para .NET Framework, esta funcionalidad generalmente solo está disponible en aplicaciones de plena confianza, debido a las evidentes implicaciones de seguridad de cargar archivos en aplicaciones a medida que se ejecutan.

## <a name="see-also"></a>Consulte también

- [Detalles de la sintaxis XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [Clases XAML y personalizadas para WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Espacio de nombres de XAML (x:) Características del lenguaje](../xaml-services/namespace-language-features.md)
- [Extensiones XAML de WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [Información general sobre elementos base](../../framework/wpf/advanced/base-elements-overview.md)
- [Árboles en WPF](../../framework/wpf/advanced/trees-in-wpf.md)
