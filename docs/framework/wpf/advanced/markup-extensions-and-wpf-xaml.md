---
title: Extensiones de marcado y XAML
ms.date: 03/30/2017
helpviewer_keywords:
- brace character [WPF]
- Binding markup extensions [WPF]
- RelativeSource markup extensions [WPF]
- XAML [WPF], markup extensions
- markup extensions [WPF]
- nesting extension syntax [WPF]
- curly brace characters ({})
- TemplateBinding markup extensions [WPF]
- StaticResource markup extensions [WPF]
- literal curly brace characters ({})
- characters [WPF], curly brace
- DynamicResource markup extensions [WPF]
ms.assetid: 618dc745-8b14-4886-833f-486d2254bb78
ms.openlocfilehash: f4134e9d0b26135d1bd6058ac9ed8941a9c6be34
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727888"
---
# <a name="markup-extensions-and-wpf-xaml"></a>Extensiones de marcado y XAML de WPF
En este tema se presenta el concepto de extensiones de marcado para XAML, incluidos sus reglas de sintaxis, su finalidad y el modelo de objeto de clase subyacente. Las extensiones de marcado son una característica general del lenguaje XAML y de la implementación .NET de servicios XAML. En este tema se detallan las extensiones de marcado para su uso en XAML de WPF.  

<a name="XAML_Processors_and_Markup_Extensions"></a>   
## <a name="xaml-processors-and-markup-extensions"></a>Procesadores XAML y extensiones de marcado  
 Por lo general, un analizador de XAML puede interpretar un valor de atributo como una cadena literal que se puede convertir a un primitivo o convertir a un objeto de algún modo. Uno de estos modos es haciendo referencia a un convertidor de tipos: se documenta en el tema [Clases TypeConverter y XAML](typeconverters-and-xaml.md). Sin embargo, hay escenarios donde se necesita un comportamiento diferente. Por ejemplo, un procesador XAML puede recibir la orden de que un valor de un atributo no debería producir un nuevo objeto en el gráfico de objetos. En su lugar, el atributo debería producir un gráfico de objeto que hiciera referencia a un objeto ya construido en otra parte del gráfico o un objeto estático. Otro escenario es que un procesador XAML puede recibir una orden para usar una sintaxis que proporciona argumentos no predeterminados al constructor de un objeto. Estos son los tipos de escenario donde una extensión de marcado puede proporcionar la solución.  
  
<a name="Basic_Markup_Extension_Syntax"></a>   
## <a name="basic-markup-extension-syntax"></a>Sintaxis de extensiones de marcado básica  
 Una extensión de marcado se puede implementar para proporcionar valores a propiedades en un uso de atributos, a propiedades en un uso de elementos de propiedad o ambos usos.  
  
 Cuando se usa para proporcionar un valor de atributo, la sintaxis que distingue una secuencia de extensión de marcado para un procesador XAML es la presencia de llaves de apertura y cierre ({ y }). A continuación, el token de cadena inmediatamente posterior a la llave de apertura identifica el tipo de extensión de marcado.  
  
 Cuando se usa en la sintaxis de elemento de propiedad, una extensión de marcado es visualmente igual que cualquier otro elemento que se use para proporcionar un valor de elemento de propiedad: una declaración de elemento XAML que hace referencia a la clase de extensión de marcado como un elemento, incluido entre corchetes angulares (<>).  
  
<a name="XAML_Defined_Markup_Extensions"></a>   
## <a name="xaml-defined-markup-extensions"></a>Extensiones de marcado definidas por XAML  
 Existen varias extensiones de marcado que no son específicas de la implementación de WPF de XAML, pero que son implementaciones intrínsecas o características de XAML como lenguaje. Estas extensiones de marcado se implementan en el ensamblado System.Xaml como parte de los servicios XAML de .NET Framework generales y están dentro del espacio de nombres XAML del lenguaje XAML. En cuanto al uso de marcación común, estas extensiones de marcado se suelen identificar por el prefijo `x:` en el uso. La clase base <xref:System.Windows.Markup.MarkupExtension> (también definida en System. xaml) proporciona el patrón que deben usar todas las extensiones de marcado para que se admita en lectores XAML y escritores de XAML, incluido en XAML de WPF.  
  
- `x:Type` proporciona el objeto <xref:System.Type> para el tipo con nombre. Esta función se usa con más frecuencia en estilos y plantillas. Para obtener más información, consulte [x:Type (Extensión de marcado)](../../../desktop-wpf/xaml-services/xtype-markup-extension.md).  
  
- `x:Static` genera valores estáticos. Los valores proceden de entidades de código de tipo de valor que no son directamente el tipo del valor de una propiedad de destino, pero que se pueden evaluar como ese tipo. Para obtener más información, consulte [Extensiones de marcado x:Static](../../../desktop-wpf/xaml-services/xstatic-markup-extension.md).  
  
- `x:Null` especifica `null` como un valor para una propiedad y se puede usar para atributos o valores de elemento de propiedad. Para obtener más información, consulte [x:Null (Extensión de marcado)](../../../desktop-wpf/xaml-services/xnull-markup-extension.md).  
  
- `x:Array` admite la creación de matrices generales en sintaxis XAML para casos en los que no se use deliberadamente el soporte de colección que proporcionan los elementos base y los modelos de control. Para obtener más información, consulte [x:Array (Extensión de marcado)](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).  
  
> [!NOTE]
> El prefijo `x:` se usa para la asignación de espacio de nombres típica de XAML para los objetos intrínsecos del lenguaje XAML, en el elemento raíz de una producción o un archivo XAML. Por ejemplo, las plantillas de Visual Studio para aplicaciones de WPF inician un archivo XAML usando esta asignación de `x:`. Puede elegir un token de prefijo diferente en su propia asignación de espacio de nombres XAML, pero en esta documentación se presupone la asignación `x:` predeterminada como manera de identificar las entidades que forman una parte definida del espacio de nombres XAML del lenguaje XAML, en lugar de un espacio de nombres predeterminado de WPF o de otros espacios de nombres XAML que no estén relacionados con ningún marco específico.  
  
<a name="WPF_Specific_Markup_Extensions"></a>   
## <a name="wpf-specific-markup-extensions"></a>Extensiones de marcado específicas de WPF  
 Las extensiones de marcado más comunes que se usan en la programación de WPF son las que admiten referencias de recursos (`StaticResource` y `DynamicResource`) y las que admiten el enlace de datos (`Binding`).  
  
- `StaticResource` proporciona un valor para una propiedad sustituyendo el valor de un recurso ya definido. Finalmente, se realiza una evaluación `StaticResource` en tiempo de carga XAML y no tiene acceso al gráfico de objetos en tiempo de ejecución. Para obtener más información, consulte [Extensión de marcado StaticResource](staticresource-markup-extension.md).  
  
- `DynamicResource` proporciona un valor para una propiedad aplazando ese valor para que sea una referencia a un recurso en tiempo de ejecución. Una referencia de recurso dinámico fuerza una nueva búsqueda cada vez que se tiene acceso a este tipo de recurso y tiene acceso al gráfico de objetos en tiempo de ejecución. Para obtener este acceso, las propiedades de dependencia del sistema de propiedades de WPF y las expresiones evaluadas admiten el concepto `DynamicResource`. Por lo tanto, solo puede usar `DynamicResource` para un destino de propiedad de dependencia. Para obtener más información, consulte [Extensión de marcado DynamicResource](dynamicresource-markup-extension.md).  
  
- `Binding` proporciona un valor enlazado a datos para una propiedad mediante el contexto de datos que se aplica al objeto primario en tiempo de ejecución. Esta extensión de marcado es relativamente compleja, porque permite una sintaxis insertada sustancial para especificar un enlace de datos. Para obtener más información, consulte [Binding (extensión de marcado)](binding-markup-extension.md).  
  
- `RelativeSource` proporciona información de origen para una <xref:System.Windows.Data.Binding> que puede navegar por varias posibles relaciones en el árbol de objetos en tiempo de ejecución. Esto proporciona un origen especializado para los enlaces que se crean en plantillas de uso múltiple o creados en código sin conocimiento completo del árbol de objetos adyacente. Para obtener más información, consulte [Extensión de marcado RelativeSource](relativesource-markupextension.md).  
  
- `TemplateBinding` permite que una plantilla de control use valores para propiedades con plantilla procedentes de propiedades definidas por el modelo de objeto de la clase que usará la plantilla. En otras palabras, la propiedad dentro de la definición de plantilla puede obtener acceso a un contexto que solo existe cuando se aplica la plantilla. Para obtener más información, consulte [Extensión de marcado TemplateBinding](templatebinding-markup-extension.md). Para obtener más información sobre el uso práctico de `TemplateBinding`, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
- `ColorConvertedBitmap` admite un escenario de creación de imágenes relativamente avanzado. Para obtener más información, consulte [ColorConvertedBitmap (extensión de marcado)](colorconvertedbitmap-markup-extension.md).  
  
- `ComponentResourceKey` y `ThemeDictionary` admiten aspectos de búsqueda de recursos, especialmente para recursos y temas que se empaquetan con controles personalizados. Para obtener más información, consulte [Extensión de marcado ComponentResourceKey](componentresourcekey-markup-extension.md), [Extensión de marcado ThemeDictionary](themedictionary-markup-extension.md) o [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
<a name="StarExtension"></a>   
## <a name="extension-classes"></a>Clases de extensión de \*  
 Tanto para el lenguaje XAML general como para las extensiones de marcado específicas de WPF, el comportamiento de cada extensión de marcado se identifica como un procesador XAML a través de una clase `*Extension` que se deriva de <xref:System.Windows.Markup.MarkupExtension>y proporciona una implementación del método <xref:System.Windows.Markup.StaticExtension.ProvideValue%2A>. Este método de cada extensión proporciona el objeto que se devuelve cuando se evalúa la extensión de marcado. El objeto devuelto se suele evaluar según los distintos token de cadena que se pasan a la extensión de marcado.  
  
 Por ejemplo, la clase <xref:System.Windows.StaticResourceExtension> proporciona la implementación de la superficie de la búsqueda de recursos real para que su implementación de <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> devuelva el objeto que se solicita, con la entrada de esa implementación concreta como una cadena que se usa para buscar el recurso por su `x:Key`. Gran parte de este detalle de implementación no es importante si usa una extensión de marcado existente.  
  
 Algunas extensiones de marcado no usan argumentos de token de cadena. Esto es porque devuelven un valor estático o coherente o porque el contexto para el valor que se debe devolver está disponible mediante uno de los servicios que se pasan con el parámetro `serviceProvider`.  
  
 El patrón de nomenclatura `*Extension` es por comodidad y coherencia. No es necesario para que un procesador XAML identifique esa clase como compatible para una extensión de marcado. Siempre que el código base incluya System. XAML y use .NET Framework implementaciones de servicios XAML, todo lo que se necesita para que se reconozca como una extensión de marcado XAML es derivar de <xref:System.Windows.Markup.MarkupExtension> y admitir una sintaxis de construcción. WPF define las clases de habilitación de la extensión de marcado que no siguen el patrón de nomenclatura `*Extension`, por ejemplo <xref:System.Windows.Data.Binding>. Normalmente, el motivo es que la clase admite escenarios más allá de la compatibilidad de extensión de marcado pura. En el caso de <xref:System.Windows.Data.Binding>, esa clase admite el acceso en tiempo de ejecución a los métodos y propiedades del objeto para los escenarios que no tienen nada que hacer con XAML.  
  
### <a name="extension-class-interpretation-of-initialization-text"></a>Interpretación de la clase de extensión del texto de inicialización  
 Un procesador XAML interpreta los token de cadena que siguen el nombre de la extensión de marcado y están dentro de las llaves de las siguientes maneras:  
  
- Una coma siempre representa el separador o el delimitador de token individuales.  
  
- Si los token separados individuales no contienen ningún signo igual, cada token se trata como un argumento constructor. Cada parámetro constructor debe proporcionarse como el tipo que espera la signatura y en el orden apropiado que espera la signatura.  
  
    > [!NOTE]
    > Un procesador XAML debe llamar al constructor que coincida con el recuento de argumentos del número de pares. Por esta razón, si está implementando una extensión de marcado personalizada, no proporcione varios constructores con el mismo recuento de argumentos. El comportamiento de cómo se comporta un procesador XAML si existe más de una ruta de acceso de constructor de extensión de marcado con el mismo recuento de parámetros no está definido, pero debe prever que un procesador XAML puede producir una excepción en el uso si esta situación se da en las definiciones de tipo de las extensiones de marcado.  
  
- Si los tokens separados individuales contienen signos de igual, un procesador XAML llama primero al constructor sin parámetros para la extensión de marcado. A continuación, cada par nombre=valor se interpreta como un nombre de propiedad que existe en la extensión de marcado y un valor que se asigna a esa propiedad.  
  
- Si hay un resultado paralelo entre el comportamiento del constructor y el comportamiento de la configuración de propiedades en una extensión de marcado, no importa qué comportamiento use. Es más común usar los pares *propiedad*`=`*valor* pares para las extensiones de marcado que tienen más de una propiedad configurable, aunque solamente sea porque hace que la marcación sea más calculada y es menos probable transponer accidentalmente parámetros constructor. (Cuando se especifican pares propiedad = valor, esas propiedades pueden estar en cualquier orden). Además, no hay ninguna garantía de que una extensión de marcado suministre un parámetro de constructor que establezca cada una de sus propiedades configurables. Por ejemplo, <xref:System.Windows.Data.Binding> es una extensión de marcado, con muchas propiedades que se pueden establecer a través de la extensión en el formato de *valor* de *propiedad*`=`, pero <xref:System.Windows.Data.Binding> solo admite dos constructores: un constructor sin parámetros y otro que establece una ruta de acceso inicial.  
  
- Una coma literal no se puede pasar a una extensión de marcado sin escape.  
  
<a name="EscapeSequences"></a>   
## <a name="escape-sequences-and-markup-extensions"></a>Secuencias de escape y extensiones de marcado  
 El control de atributos en un procesador XAML usa las llaves como indicadores de una secuencia de extensión de marcado. También es posible generar un valor de atributo de caracteres literales de llave si es necesario, escribiendo una secuencia de escape con un par de llaves vacío seguido de la llave de cierre literal. Vea [{} extensión de marcado de secuencia de escape](../../../desktop-wpf/xaml-services/escape-sequence-markup-extension.md).  
  
<a name="Nesting"></a>   
## <a name="nesting-markup-extensions-in-xaml-usage"></a>Anidar extensiones de marcado en uso de XAML  
 Se admite el anidamiento de varias extensiones de marcado. Se empezará a evaluar las extensiones de marcado por profundidad. Por ejemplo, considere el siguiente uso:  
  
```xaml  
<Setter Property="Background"  
  Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}" />  
```  
  
 En este uso, la instrucción `x:Static` se evalúa primero y devuelve una cadena. A continuación, la cadena se usa como argumento para `DynamicResource`.  
  
## <a name="markup-extensions-and-property-element-syntax"></a>Extensiones de marcado y sintaxis de elementos de propiedad  
 Cuando se usa como un elemento de objeto que rellena un valor de elemento de propiedad, una clase de extensión de marcado es visualmente indistinguible de un elemento de objeto típico respaldado por tipo que se puede usar en XAML. La diferencia práctica entre un elemento de objeto típico y una extensión de marcado es que la extensión de marcado se evalúa como un valor con tipo o se aplaza como una expresión. Por lo tanto, los mecanismos para detectar posibles errores de tipo de valores de propiedad para la extensión de marcado será diferente, de forma similar a cómo se trata una propiedad enlazada en tiempo de ejecución en otros modelos de programación. Se evaluará un elemento de objeto normal para la coincidencia de tipo con la propiedad de destino que se configura al analizar el XAML.  
  
 La mayoría de extensiones de marcado, cuando se usan en sintaxis de elementos de objeto para rellenar un elemento de propiedad, no contienen sintaxis de elementos de contenido o de cualquier otra propiedad. De este modo, cerraría la etiqueta de elemento de objeto y no proporcionaría ningún elemento secundario. Siempre que un procesador XAML encuentra cualquier elemento de objeto, se llama al constructor de esa clase, que crea una instancia del objeto creado a partir del elemento analizado. Una clase de extensión de marcado no es diferente: Si desea que la extensión de marcado se pueda usar en la sintaxis de elementos de objeto, debe proporcionar un constructor sin parámetros. Algunas extensiones de marcado existentes tienen al menos un valor de propiedad obligatorio que se debe especificar para obtener una inicialización eficaz. Si es así, ese valor de propiedad se proporciona normalmente como un atributo de propiedad en el elemento de objeto. En las páginas de referencia [Características de lenguaje (x:) de espacios de nombres XAML](../../../desktop-wpf/xaml-services/namespace-language-features.md) y [Extensiones XAML de WPF](wpf-xaml-extensions.md), se indican las extensiones de marcado que tienen propiedades obligatorias (y los nombres de dichas propiedades). En las páginas de referencia también se indica si la sintaxis de elementos de objeto o de atributos no se permite para extensiones de marcado concretas. Un caso destacado e es [x:Array (Extensión de marcado)](../../../desktop-wpf/xaml-services/xarray-markup-extension.md), que no admite la sintaxis de atributos porque el contenido de la matriz debe especificarse en el etiquetado como contenido. El contenido de la matriz se controla como objetos generales y, por lo tanto, no es posible usar ningún convertidor de tipos predeterminado para el atributo. Además, [x:Array (Extensión de marcado)](../../../desktop-wpf/xaml-services/xarray-markup-extension.md) necesita un parámetro `type`.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Características de lenguaje (x:) de espacios de nombres XAML](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [Extensiones XAML de WPF](wpf-xaml-extensions.md)
- [StaticResource (extensión de marcado)](staticresource-markup-extension.md)
- [Binding (extensión de marcado)](binding-markup-extension.md)
- [DynamicResource (extensión de marcado)](dynamicresource-markup-extension.md)
- [x:Type (extensión de marcado)](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
