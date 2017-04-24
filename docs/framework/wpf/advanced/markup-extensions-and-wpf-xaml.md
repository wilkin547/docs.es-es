---
title: "Extensiones de marcado y XAML de WPF | Microsoft Docs"
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
  - "*Extension (clase)"
  - "Binding (extensión de marcado)"
  - "llave (carácter)"
  - "caracteres, llave"
  - "clases, MarkupExtension"
  - "{} (caracteres de llave)"
  - "DynamicResource (extensión de marcado)"
  - "caracteres literales de llave ({})"
  - "extensiones de marcado"
  - "MarkupExtension (clase)"
  - "sintaxis de extensiones anidadas"
  - "RelativeSource (extensiones de marcado)"
  - "StaticResource (extensión de marcado)"
  - "TemplateBinding (extensión de marcado)"
  - "XAML, extensiones de marcado"
ms.assetid: 618dc745-8b14-4886-833f-486d2254bb78
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Extensiones de marcado y XAML de WPF
En este tema se presenta el concepto de extensiones de marcado para XAML, incluidas sus reglas de sintaxis, propósito y modelo de objetos de clase subyacente.  Las extensiones de marcado son una característica general del lenguaje XAML y de la implementación de .NET de servicios XAML.  En este tema se detallan las extensiones de marcado para uso en XAML de WPF.  
  
   
  
<a name="XAML_Processors_and_Markup_Extensions"></a>   
## Procesadores de XAML y extensiones de marcado  
 Hablando en general, un analizador de XAML puede interpretar un valor de atributo como una cadena literal que se puede convertir en una primitiva o en un objeto por algún medio.  Uno de estos medios es haciendo referencia a un convertidor de tipos; esto se documenta en el tema [Clases TypeConverter y XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  No obstante, hay escenarios donde se requiere un comportamiento diferente.  Por ejemplo, se puede indicar a un procesador de XAML que un valor de un atributo no debe producir un nuevo objeto en el gráfico de objetos.  En cambio, el atributo debería producir un gráfico de objetos que hace una referencia a un objeto ya construido en otra parte del grafo o en un objeto estático.  Otro escenario es que se puede indicar a un procesador de XAML que utilice una sintaxis que proporcione argumentos no predeterminados al constructor de un objeto. Éstos son los tipos de escenarios en los que una extensión de marcado puede proporcionar la solución.  
  
<a name="Basic_Markup_Extension_Syntax"></a>   
## Sintaxis básica de extensión de marcado  
 Se puede implementar una extensión de marcado para que proporcione valores para las propiedades de un uso de atributo, las propiedades de un uso de elemento de propiedad o ambas.  
  
 Cuando se utiliza para proporcionar un valor de atributo, la sintaxis que distingue una secuencia de extensión de marcado de un procesador de XAML es la presencia de llaves de apertura y cierre \({ y }\).  El token de cadena que sigue inmediatamente a la llave de apertura identifica el tipo de extensión de marcado.  
  
 Cuando se utiliza en la sintaxis de elementos de propiedad, una extensión de marcado es visualmente igual que cualquier otro elemento utilizado para proporcionar un valor de elemento de propiedad: una declaración de elemento XAML que hace referencia a la clase de extensión de marcado como un elemento, delimitada por corchetes angulares \(\< \>\).  
  
<a name="XAML_Defined_Markup_Extensions"></a>   
## Extensiones de marcado definidas por XAML  
 Existen varias extensiones de marcado que no son específicas de la implementación WPF de XAML, sino que son implementaciones de elementos intrínsecos o características del XAML como lenguaje.  Estas extensiones de marcado se implementan en el ensamblado System.Xaml como parte de los servicios generales XAML de .NET Framework y están dentro del espacio de nombres XAML del lenguaje XAML.  Por lo que se refiere al uso de marcado común, estas extensiones de marcado son típicamente identificables por el prefijo `x:`.  La clase base <xref:System.Windows.Markup.MarkupExtension> \(también definida en System.Xaml\) proporciona el modelo que todas las extensiones de marcado deben utilizar para ser compatibles con los lectores y sistemas de escritura XAML, incluido XAML de WPF.  
  
-   `x:Type` proporciona el objeto <xref:System.Type> para el tipo nombrado.  Esta capacidad se utiliza con más frecuencia en estilos y plantillas.  Para obtener información detallada, vea [x:Type \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-type-markup-extension.md).  
  
-   `x:Static` genera valores estáticos.  Los valores provienen de entidades de código de tipo de valor que no son directamente el tipo de un valor de una propiedad de destino, pero se pueden evaluar como ese tipo.  Para obtener información detallada, vea [Extensiones de marcado x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md).  
  
-   `x:Null` especifica `null` como un valor de una propiedad y se puede utilizar para atributos o valores de elemento de propiedad.  Para obtener información detallada, vea [x:Null \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
-   `x:Array` proporciona compatibilidad para la creación de matrices generales en la sintaxis de XAML, para aquellos casos en los que la compatibilidad de colección proporcionada por los elementos base y los modelos de control de WPF no se utiliza deliberadamente.  Para obtener información detallada, vea [x:Array \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-array-markup-extension.md).  
  
> [!NOTE]
>  El prefijo `x:` se utiliza para la asignación típica del espacio de nombres en XAML de los elementos intrínsecos del lenguaje XAML, en el elemento raíz de un archivo XAML o de producción.  Por ejemplo, las plantillas de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] para aplicaciones de WPF inician un archivo XAML mediante esta asignación `x:`.  Podría elegir un token de prefijo diferente en su propia asignación de espacio de nombres XAML, pero en esta documentación se supone la asignación de `x:` predeterminada como medio para identificar esas entidades que constituyen una parte definida del espacio de nombres XAML del lenguaje XAML, para diferenciarlas del espacio de nombres predeterminado de WPF o de otros espacios de nombres XAML no relacionados con un marco específico.  
  
<a name="WPF_Specific_Markup_Extensions"></a>   
## Extensiones de marcado específicas de WPF  
 Las extensiones de marcado más comunes utilizadas en la programación de WPF son las que admiten referencias de recursos \(`StaticResource` y `DynamicResource`\) y las que admiten el enlace de datos \(`Binding`\).  
  
-   `StaticResource` proporciona un valor para una propiedad sustituyendo el valor de un recurso ya definido.  Una evaluación de `StaticResource` se realiza finalmente en tiempo de carga de XAML y no tiene acceso al gráfico de objetos en tiempo de ejecución. Para obtener información detallada, vea [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   `DynamicResource` proporciona un valor para una propiedad aplazando ese valor para que sea una referencia a un recurso en tiempo de ejecución.  Una referencia de recurso dinámico fuerza una nueva búsqueda cada vez que se obtiene acceso a este tipo de recurso y tiene acceso en tiempo de ejecución al gráfico de objetos.  Con el fin de obtener este acceso, el concepto `DynamicResource` lo admiten las propiedades de dependencia del sistema de propiedades de WPF, y las expresiones evaluadas.  Por consiguiente, solo puede usar `DynamicResource` para un destino de la propiedad de dependencia.  Para obtener información detallada, vea [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
-   `Binding` proporciona un valor enlazado a datos para una propiedad, utilizando el contexto de datos que se aplica al objeto primario en tiempo de ejecución.  Esta extensión de marcado es relativamente compleja, porque habilita una sintaxis fundamentalmente incluida en el propio código para especificar un enlace de datos.  Para obtener información detallada, vea [Enlazar extensión de marcado](../../../../docs/framework/wpf/advanced/binding-markup-extension.md).  
  
-   `RelativeSource` proporciona información de origen para un objeto <xref:System.Windows.Data.Binding> que puede navegar por varias posibles relaciones en el árbol de objetos en tiempo de ejecución.  Esto proporciona una fuente especializada para los enlaces que se crean en plantillas de uso múltiple o se crean en código sin conocimiento completo del árbol de objetos circundante.  Para obtener información detallada, vea [Extensión de marcado RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md).  
  
-   `TemplateBinding` permite que una plantilla de control utilice valores para propiedades con plantilla procedentes de propiedades definidas por el modelo de objetos de la clase que utilizará la plantilla.  En otras palabras, la propiedad incluida en la definición de la plantilla puede tener acceso a un contexto que solo exista una vez aplicada la plantilla.  Para obtener información detallada, vea [Extensión de marcado TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  Para obtener más información sobre el uso práctico de `TemplateBinding`, vea [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
-   `ColorConvertedBitmap` admite un escenario de creación de imágenes relativamente avanzado.  Para obtener información detallada, vea [Extensión de marcado ColorConvertedBitmap](../../../../docs/framework/wpf/advanced/colorconvertedbitmap-markup-extension.md).  
  
-   `ComponentResourceKey` y `ThemeDictionary` admiten aspectos de la búsqueda de recursos, en concreto para los recursos y temas que se empaquetan con controles personalizados.  Para obtener más información, vea [Extensión de marcado ComponentResourceKey](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md), [Extensión de marcado ThemeDictionary](../../../../docs/framework/wpf/advanced/themedictionary-markup-extension.md) o [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="StarExtension"></a>   
## Clases \*Extension  
 Para las extensiones de marcado específicas de WPF y del lenguaje XAML general, el comportamiento de cada extensión de marcado se identifica para un procesador de XAML a través de una clase `*Extension` que deriva de <xref:System.Windows.Markup.MarkupExtension> y proporciona una implementación del método <xref:System.Windows.Markup.StaticExtension.ProvideValue%2A>.  Este método en cada extensión proporciona el objeto que se devuelve una vez que se evalúa la extensión de marcado.  El objeto devuelto normalmente se evalúa según los distintos tokens de cadena que se pasan a la extensión de marcado.  
  
 Por ejemplo, la clase <xref:System.Windows.StaticResourceExtension> proporciona la implementación de superficie de la búsqueda real de recursos, de modo que su implementación <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> devuelva el objeto que se solicita, siendo la entrada de esa implementación en particular una cadena que se utiliza para buscar el recurso por su `x:Key`.  Gran parte de este detalle de implementación es irrelevante si se está utilizando una extensión de marcado existente.  
  
 Algunas extensiones de marcado no utilizan argumentos de token de cadena.  Esto se debe a que devuelven un valor estático o coherente, o a que el contexto del valor que se debe devolver está disponible a través de uno de los servicios pasados a través del parámetro `serviceProvider`.  
  
 El modelo de nombres `*Extension` se usa por comodidad y coherencia.  No es necesario para que un procesador de XAML identifique esa clase como compatibilidad para una extensión de marcado.  Siempre que el código base incluya System.Xaml y utilice implementaciones de Servicios XAML de .NET Framework, todo lo que necesita para que sea reconocido como una extensión de marcado XAML es que derive de <xref:System.Windows.Markup.MarkupExtension> y admita una sintaxis de construcción.  WPF define las clases que habilitan la extensión de marcado que no siguen el modelo de nombres `*Extension`, por ejemplo <xref:System.Windows.Data.Binding>.  El motivo suele ser que la clase admite escenarios que van más allá de la mera compatibilidad con la extensión de marcado.  En el caso de <xref:System.Windows.Data.Binding>, esa clase admite el acceso en tiempo de ejecución a métodos y propiedades del objeto para escenarios que no tienen nada que ver con XAML.  
  
### Interpretación de clase de extensión de texto de inicialización  
 Los tokens de cadena que siguen al nombre de extensión de marcado y siguen dentro de las llaves los interpreta un procesador de XAML de una de las siguientes maneras:  
  
-   Una coma siempre representa el separador o el delimitador de token individuales.  
  
-   Si los token separados individuales no contienen ningún signo igual, cada token se trata como un argumento de constructor.  Cada parámetro de constructor se debe proporcionar como el tipo esperado por esa firma y en el orden apropiado esperado por esa firma.  
  
    > [!NOTE]
    >  Un procesador de XAML debe llamar al constructor que coincida con el recuento de argumentos del número de pares.  Por esta razón, si está implementando una extensión de marcado personalizada, no proporcione el mismo recuento de argumentos a varios parámetros.  El comportamiento de cómo se comporta un procesador de XAML si existe más de una ruta de acceso de constructor de extensión de marcado con el mismo recuento de parámetros no está definido, pero debe prever que a un procesador de XAML se le permite generar una excepción en su uso si existe esta situación en las definiciones de los tipos de extensión de marcado.  
  
-   Si los tokens separados individuales contienen signos igual, un procesador de XAML llama primero al constructor predeterminado de la extensión de marcado.  A continuación, cada par nombre\=valor se interpreta como un nombre de propiedad que existe en la extensión de marcado y un valor que asignar a esa propiedad.  
  
-   Si hay un resultado paralelo entre el comportamiento del constructor y el comportamiento de configuración de propiedad en una extensión de marcado, no importa qué comportamiento utilice.  Es más común utilizar los pares *propiedad*`=`*valor* para extensiones de marcado que tengan más de una propiedad configurable, aunque solamente sea porque hace que el marcado sea más calculado y sea menos probable que se transpongan accidentalmente los parámetros de constructor.  \(Al especificar los pares propiedad\=valor, esas propiedades pueden estar en cualquier orden\). Además, no hay ninguna garantía de que una extensión de marcado proporcione un parámetro de constructor que establezca todas sus propiedades configurables.  Por ejemplo, <xref:System.Windows.Data.Binding> es una extensión de marcado, con muchas propiedades que se pueden configurar a través de la extensión en la forma *propiedad*`=`*valor*, pero <xref:System.Windows.Data.Binding> solamente admite dos constructores: un constructor predeterminado y uno que establece una ruta de acceso inicial.  
  
-   Una coma literal no se puede pasar a una extensión de marcado sin escape.  
  
<a name="EscapeSequences"></a>   
## Secuencias de escape y extensiones de marcado  
 El control de atributos en un procesador de XAML utiliza las llaves como indicadores de una secuencia de extensión de marcado.  También es posible producir un valor de atributo de carácter de llave literal si es necesario, escribiendo una secuencia de escape con un par de llaves vacío seguido por la llave literal.  Vea [Secuencia de escape \/ extensión de marcado {}](../../../../docs/framework/xaml-services/escape-sequence-markup-extension.md).  
  
<a name="Nesting"></a>   
## Anidar las extensiones de marcado en el uso de XAML  
 Se permite anidar varias extensiones de marcado y se evalúa en primer lugar la extensión de marcado más profunda.  Por ejemplo, considere la siguiente sintaxis:  
  
```  
<Setter Property="Background"  
  Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}" />  
  
```  
  
 En esta sintaxis, la instrucción `x:Static` se evalúa primero y devuelve una cadena.  Esa cadena se utiliza como argumento de `DynamicResource`.  
  
## Extensiones de marcado y sintaxis de elementos de propiedad  
 Cuando se utiliza como un elemento de objeto que rellena un valor de elemento de propiedad, una clase de extensión de marcado es visualmente indistinguible de un elemento de objeto respaldado por tipos común que se puede utilizar en XAML.  La diferencia práctica entre un elemento de objeto común y una extensión de marcado es que la extensión de marcado se evalúa como un valor con tipo o se aplaza como una expresión.  Por consiguiente, los mecanismos de cualquier posible error de tipo de los valores de propiedad para la extensión de marcado serán diferentes, de forma similar a como se trata una propiedad enlazada en tiempo de ejecución en otros modelos de programación.  Un elemento de objeto ordinario se evaluará para la coincidencia de tipos con la propiedad de destino que se está estableciendo cuando se analiza el XAML.  
  
 La mayoría de las extensiones de marcado, cuando se utilizan en la sintaxis de elemento de objeto para rellenar un elemento de propiedad, no tendrían ningún contenido ni ninguna otra sintaxis de elemento de propiedad.  Por lo tanto, se cerraría la etiqueta de elemento del objeto y no se proporcionaría ningún elemento secundario.  Siempre que un procesador de XAML encuentra un elemento de objeto, se llama al constructor de esa clase para crear una instancia del objeto creado a partir del elemento analizado.  Una clase de extensión de marcado no es diferente: si se desea que la extensión de marcado sea utilizable en la sintaxis de elementos de objeto, se debe proporcionar un constructor predeterminado.  Algunas extensiones de marcado existentes tienen por lo menos un valor de propiedad necesario que debe especificarse para la inicialización efectiva.  Si es así, ese valor de propiedad suele proporcionarse como un atributo de propiedad en el elemento de objeto.  En las páginas de referencia [Características de lenguaje \(x:\) de espacios de nombres XAML](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md) y [Extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md) se indicarán las extensiones de marcado que tienen propiedades obligatorias \(y los nombres de las propiedades obligatorias\).  Las páginas de referencia también indican si se deniega la sintaxis de elemento de objeto o la sintaxis de atributo para extensiones de marcado determinadas.  Un caso notable es [x:Array \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-array-markup-extension.md), que no admite la sintaxis de atributo porque el contenido de esa matriz se debe especificar dentro del etiquetado como contenido.  El contenido de la matriz se administra como objetos generales; por consiguiente, no hay ningún convertidor de tipos predeterminado factible para el atributo.  Además, [x:Array \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-array-markup-extension.md) requiere un parámetro `type`.  
  
## Vea también  
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Características de lenguaje \(x:\) de espacios de nombres XAML](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [Extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [Enlazar extensión de marcado](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)   
 [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)   
 [x:Type \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-type-markup-extension.md)