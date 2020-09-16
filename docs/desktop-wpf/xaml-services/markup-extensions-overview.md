---
title: Información general sobre las extensiones de marcado para el lenguaje XAML
ms.date: 03/30/2017
helpviewer_keywords:
- markup extensions [XAML Services], custom
- XAML [XAML Services], markup extensions
ms.assetid: 261b2b11-2dc0-462f-8c66-55b8c9c6e436
ms.openlocfilehash: efb41f31a3baa895b5739021af5fa36e32aefeea
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556998"
---
# <a name="overview-of-markup-extensions-for-xaml"></a>Información general sobre las extensiones de marcado para XAML

Las extensiones de marcado son una técnica XAML para obtener un valor que no es un tipo primitivo ni un tipo XAML específico. Para el uso de atributos, las extensiones de marcado usan la secuencia de caracteres conocida de una llave de apertura `{` para entrar en el ámbito de la extensión de marcado y una llave de cierre `}` para salir. Al usar los servicios XAML de .NET, puede usar algunas de las extensiones de marcado del lenguaje XAML predefinidas del ensamblado System. Xaml. También puede crear subclases de la clase <xref:System.Windows.Markup.MarkupExtension> , definida en System.Xaml, y definir sus propias extensiones de marcado. O bien, puede usar las extensiones de marcado definidas por un marco determinado si ya hace referencia a esa plataforma.

Cuando se accede al uso de una extensión de marcado, el escritor de objetos XAML puede proporcionar servicios a una clase <xref:System.Windows.Markup.MarkupExtension> personalizada a través de un punto de conexión de servicio en la invalidación <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A?displayProperty=nameWithType> . Los servicios pueden usarse para obtener contexto sobre el uso, las capacidades concretas del escritor de objetos, el contexto de esquema XAML, etcétera.

## <a name="xaml-defined-markup-extensions"></a>Extensiones de marcado definidas por XAML

Varias extensiones de marcado se implementan mediante los servicios XAML de .NET para la compatibilidad con el lenguaje XAML. Estas extensiones de marcado corresponden a las partes de la especificación de XAML como lenguaje. Suelen identificarse por el prefijo `x:` en la sintaxis, tal como se muestra en el uso común. Todas las implementaciones de servicios XAML de .NET para estos elementos del lenguaje XAML derivan de la  <xref:System.Windows.Markup.MarkupExtension> clase base.

> [!NOTE]
> El prefijo `x:` se usa para la asignación de espacio de nombres típica de XAML para el espacio de nombres del lenguaje XAML, en el elemento raíz de una producción de XAML. Por ejemplo, las plantillas de proyecto y de página de Visual Studio para varios marcos de trabajo específicos inician un archivo XAML con esta `x:` asignación. Puede elegir un token de prefijo diferente en su propia asignación de espacio de nombres XAML, pero en esta documentación se presupone la asignación `x:` predeterminada como manera de identificar las entidades que forman una parte definida del espacio de nombres XAML del lenguaje XAML, en lugar de un espacio de nombres XAML predeterminado de un marco concreto o de otros espacios de nombres XML o CLR arbitrarios.

### <a name="xtype"></a>x:Type

`x:Type` proporciona el objeto <xref:System.Type> para el tipo con nombre. Esta funcionalidad se usa con más frecuencia en los mecanismos de aplazamiento que usan el tipo CLR subyacente y la derivación de tipos como identificador o moniker de agrupación. Los estilos y plantillas WPF y su uso de las propiedades `TargetType` son un ejemplo concreto. Para obtener más información, consulta [x:Type Markup Extension](xtype-markup-extension.md).

### <a name="xstatic"></a>x:Static

`x:Static` genera valores estáticos a partir de entidades de código de tipo de valor que no son directamente el tipo del valor de una propiedad, pero que se pueden evaluar como ese tipo. Esto es útil para especificar valores que ya existen, como constantes conocidas en una definición de tipo. Para obtener más información, consulta [x:Static Markup Extension](xstatic-markup-extension.md).

### <a name="xnull"></a>x:Null

`x:Null` especifica `null` como valor para un miembro XAML. En función del diseño de tipos específicos o de conceptos de marco más amplios, `null` no es siempre un valor predeterminado para una propiedad o el valor implícito de un atributo de cadena vacía. Para obtener más información, consulta [x:Null Markup Extension](xnull-markup-extension.md).

### <a name="xarray"></a>x:Array

`x:Array` admite la creación de matrices generales en sintaxis XAML en los casos en que no se use deliberadamente el soporte de colección que proporcionan los elementos base y los modelos de control. Para obtener más información, consulta [x:Array Markup Extension](xarray-markup-extension.md). En concreto en XAML 2009, se accede a las matrices como primitivas del lenguaje, en lugar de como una extensión. Para obtener más información, consulta [XAML 2009 Language Features](xaml-2009-language-features.md).

### <a name="xreference"></a>x:Reference

`x:Reference` forma parte de XAML 2009, una extensión del lenguaje original (2006). `x:Reference` representa una referencia a otro objeto existente en un gráfico de objetos. Dicho objeto se identifica por su `x:Name`. Para obtener más información, consulta [x:Reference Markup Extension](xreference-markup-extension.md).

### <a name="other-x-constructs"></a>Otras construcciones x:

Existen otras construcciones `x:` que admiten características del lenguaje XAML, pero no se implementan como extensiones de marcado. Para obtener más información, vea [Espacio de nombres de XAML (x:) del espacio de nombres de XAML (x:)](namespace-language-features.md).

## <a name="the-markupextension-base-class"></a>Clase base MarkupExtension

Para definir una extensión de marcado personalizada que pueda interactuar con las implementaciones predeterminadas de los lectores y escritores XAML en System.Xaml, derive una clase de la clase abstracta <xref:System.Windows.Markup.MarkupExtension> . Dicha la clase tiene que invalidar un método, <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>. Puede que también tenga que definir constructores adicionales para admitir los argumentos para el uso de la extensión de marcado, así como propiedades configurables coincidentes.

A través <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> de, una extensión de marcado personalizada tiene acceso a un contexto de servicio que notifica el entorno donde un procesador XAML invoca la extensión de marcado. En la ruta de acceso de carga, suele ser <xref:System.Xaml.XamlObjectWriter> . En la ruta de acceso de guardado, suele ser <xref:System.Xaml.XamlXmlWriter>. Cada una informa del contexto de servicio como una clase interna del contexto del proveedor de servicios XAML que implementa un patrón de proveedor de servicios. Para más información sobre los servicios disponibles y lo que representan, vea [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).

La clase de extensión de marcado debe usar un nivel de acceso público; los procesadores XAML deben ser siempre capaces de crear una instancia de la clase de soporte de la extensión de marcado para usar sus servicios.

## <a name="defining-the-support-type-for-a-custom-markup-extension"></a>Definir el tipo de compatibilidad para una extensión de marcado personalizada

Al usar los servicios XAML de .NET o marcos de trabajo que se basan en los servicios XAML de .NET, tiene dos opciones para asignar un nombre al tipo de compatibilidad de la extensión de marcado. El nombre del tipo es pertinente para la manera en que los escritores de objetos XAML intentan obtener acceso e invocar un tipo de compatibilidad de la extensión de marcado cuando encuentran un uso de la extensión de marcado en XAML. Use una de las siguientes estrategias de nomenclatura:

- Asigne al tipo un nombre que coincida exactamente con el token de uso del marcado XAML. Por ejemplo, para admitir el uso de la extensión `{Collate ...}` , asigne al tipo de compatibilidad el nombre `Collate`.
- Asigne al tipo un nombre que sea el token de la cadena de uso más el sufijo `Extension`. Por ejemplo, para admitir el uso de la extensión `{Collate ...}` , asigne al tipo de compatibilidad el nombre `CollateExtension`.

Según el orden de búsqueda, primero se busca el nombre de clase con el sufijo `Extension`y, a continuación, se busca el nombre de clase sin el sufijo `Extension` .

Desde la perspectiva del uso del marcado, es válido incluir el sufijo `Extension` como parte del uso. Sin embargo, esto se comporta como si `Extension` realmente formase parte del nombre de clase, y los escritores de objetos XAML no podrían resolver una clase de compatibilidad de la extensión de marcado para ese uso si la clase de compatibilidad no tuviese el sufijo `Extension` .

### <a name="the-parameterless-constructor"></a>Constructor sin parámetros

Para todos los tipos de compatibilidad de la extensión de marcado, debe exponer un constructor sin parámetros público. Se requiere un constructor sin parámetros para cualquier caso en el que un escritor de objetos XAML cree una instancia de la extensión de marcado a partir de un uso de elemento de objeto. La compatibilidad con el uso de elementos de objeto es una expectativa lógica para una extensión de marcado, en especial para la serialización. Sin embargo, puede implementar una extensión de marcado sin un constructor público si solo desea admitir usos de atributos de la extensión de marcado.

Si el uso de la extensión de marcado no tiene ningún argumento, se requiere el constructor sin parámetros para admitir el uso.

## <a name="constructor-patterns-and-positional-arguments-for-a-custom-markup-extension"></a>Patrones de constructor y argumentos posicionales para una extensión de marcado personalizada

En una extensión de marcado con el uso previsto del argumento, los constructores públicos deben corresponderse con los modos del uso previsto. En otras palabras, si su extensión de marcado está diseñada para requerir un argumento posicional como uso válido, debe admitir un constructor público con un parámetro de entrada que tome el argumento posicional.

Por ejemplo, supongamos que la extensión de marcado `Collate` está pensada para admitir solo un modo en el que hay un argumento posicional que representa su modo, especificado como una constante de enumeración `CollationMode` . En este caso, debe haber un constructor con el formato siguiente:

```csharp
public Collate(CollationMode collationMode) {...}
```

En un nivel básico, los argumentos pasados a una extensión de marcado son una cadena, ya que se reenvían desde los valores de atributo del marcado. Puede hacer que todos los argumentos sean cadenas y trabajar con entradas en ese nivel. Sin embargo, tiene acceso a cierto procesamiento que se produce antes de que los argumentos de extensión de marcado se pasan a la clase de compatibilidad.

El procesamiento funciona conceptualmente como si la extensión de marcado fuera un objeto que se va a crear y, a continuación, se establecieran sus valores de miembro. Cada propiedad especificada que se va a establecer se evalúa de modo similar a la manera en que se puede establecer un miembro especificado en un objeto creado cuando se analiza XAML. Hay dos diferencias importantes:

- Como se indicó anteriormente, un tipo de compatibilidad de la extensión de marcado no necesita tener un constructor sin parámetros para poder crear instancias en XAML. La construcción de objetos se aplaza hasta que sus posibles argumentos en la sintaxis de texto se conviertan en tokens y se evalúen como argumentos con nombre o posicionales y se llame al constructor adecuado en ese momento.
- Los usos de las extensiones de marcado se pueden anidar. Primero se evalúa la extensión de marcado más interna. Por lo tanto, puede suponer este tipo de uso y declarar uno de los parámetros de construcción de modo que sea un tipo que requiere que se genere un convertidor de valores (como una extensión de marcado).

En el ejemplo anterior se mostró una dependencia de este procesamiento. El escritor de objetos XAML de los servicios XAML de .NET procesa los nombres constantes de enumeración en valores enumerados en un nivel nativo.

El procesamiento de sintaxis de texto de un parámetro posicional de extensión de marcado también puede basarse en un convertidor de tipos que esté asociado al tipo que se encuentra en el argumento de construcción.

Los argumentos se denominan posicionales porque el orden en que se encuentran los tokens en el uso corresponde al orden posicional del parámetro de constructor al que están asignados. Por ejemplo, considere la siguiente firma de constructor:

```csharp
public Collate(CollationMode collationMode, object collateThis) {...}
```

Un procesador XAML espera dos argumentos posicionales para esta extensión de marcado. Si hubo un uso `{Collate AlphaUp,{x:Reference circularFile}}`, el token `AlphaUp` se envía al primer parámetro y se evalúa como una enumeración denominada constante `CollationMode` . El resultado de la `x:Reference` interna se envía al segundo parámetro y se evalúa como un objeto.

En las reglas especificadas de XAML para la sintaxis y el procesamiento de la extensión de marcado, la coma es el delimitador entre los argumentos, tanto si son argumentos posicionales como argumentos con nombre.

### <a name="duplicate-arity-of-positional-arguments"></a>Aridad duplicada de argumentos posicionales

Si un escritor de objetos XAML encuentra un uso de la extensión de marcado con argumentos posicionales y hay varios argumentos de constructor que toman ese número de argumentos (una aridad duplicada), no se trata necesariamente de un error. El comportamiento depende de un valor de contexto de esquema XAML personalizable, <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A>. Si <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> es `true`, un escritor de objetos XAML no debería iniciar una excepción solo por razones de aridad duplicada. El comportamiento a partir de ese punto no está definido estrictamente. La hipótesis de diseño básica es que el contexto del esquema tiene información de tipo disponible para los parámetros específicos y puede intentar conversiones explícitas que coinciden con los candidatos duplicados para comprobar qué firma es la mejor coincidencia. Podría iniciarse igualmente una excepción si ninguna firma supera las pruebas impuestas por el contexto de esquema concreto que se ejecuta en un escritor de objetos XAML.

De forma predeterminada, <xref:System.Xaml.XamlSchemaContextSettings.SupportMarkupExtensionsWithDuplicateArity%2A> se encuentra `false` en los <xref:System.Xaml.XamlSchemaContext> servicios XAML de .net basados en CLR. Por lo tanto, el <xref:System.Xaml.XamlObjectWriter> predeterminado genera una excepción si encuentra un uso de la extensión de marcado con aridad duplicada en los constructores del tipo de respaldo.

## <a name="named-arguments-for-a-custom-markup-extension"></a>Argumentos con nombre para una extensión de marcado personalizada

Las extensiones de marcado que especifica XAML también pueden usar un formulario de argumentos con nombre para el uso. En el primer nivel de tokenización, la sintaxis de texto se divide en argumentos. La presencia de un signo igual (=) en un argumento lo identifica como argumento con nombre. Dicho argumento también se convierte en token en un par nombre-valor. En este caso, el nombre designa una propiedad pública configurable del tipo de compatibilidad de la extensión de marcado. Si piensa admitir el uso de argumentos con nombre, debe proporcionar estas propiedades públicas configurables. Las propiedades pueden ser heredadas, siempre y cuando sigan siendo públicas.

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Acceder al contexto del proveedor de servicios desde una implementación de la extensión de marcado

Los servicios disponibles son los mismos para todos los convertidores de valores. La diferencia radica en la manera en que cada convertidor de valores recibe el contexto de servicio. El acceso a los servicios y los servicios disponibles se documentan en el tema [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).

## <a name="property-element-usage-of-a-markup-extension"></a>Uso de elementos de propiedad de una extensión de marcado

Los escenarios para los usos de la extensión de marcado suelen estar diseñados para emplear la extensión de marcado en el uso de atributos. Sin embargo, también es posible definir la clase de respaldo de modo que admita el uso de elementos de propiedad.

Para admitir el uso de elementos de propiedad de la extensión de marcado, defina un constructor sin parámetros público. Debe ser un constructor de instancia, no un constructor estático. Esto es necesario porque un procesador XAML generalmente debe invocar el constructor sin parámetros en cualquier elemento de objeto que procesa desde el marcado, lo que incluye las clases de extensión de marcado como elementos de objeto. En el caso de escenarios avanzados, puede definir rutas de acceso de construcción no predeterminadas para las clases. (Para obtener más información, vea [la Directiva x:FactoryMethod](xfactorymethod-directive.md)). Sin embargo, no debe utilizar estos patrones para la extensión de marcado, ya que esto hace que la detección del patrón de uso sea mucho más difícil, tanto para diseñadores como para usuarios de marcado sin formato.

## <a name="attributing-for-a-custom-markup-extension"></a>Atribución para una extensión de marcado personalizada

Para admitir entornos de diseño y ciertos escenarios del escritor de objetos XAML, debe atribuir varios atributos CLR a un tipo de compatibilidad de la extensión de marcado. Estos atributos notifican el uso previsto de la extensión de marcado.

 <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute> notifica información <xref:System.Type> del tipo de objeto que <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> devuelve. Por su firma pura, <xref:System.Windows.Markup.ArrayExtension.ProvideValue%2A> devuelve <xref:System.Object>. Sin embargo, algunos consumidores podrían desear información más precisa sobre el tipo de valor devuelto. Esto incluye:

- Diseñadores e IDE, que pueden proporcionar compatibilidad con reconocimiento del tipo para los usos de la extensión de marcado.
- Implementaciones avanzadas de controladores `SetMarkupExtension` en las clases de destino, que podrían basarse en la reflexión para determinar el tipo de valor devuelto de una extensión de marcado, en lugar de realizar una bifurcación en implementaciones <xref:System.Windows.Markup.MarkupExtension> conocidas específicas por nombre.

## <a name="serialization-of-markup-extension-usages"></a>Serialización de los usos de la extensión de marcado

Cuando un escritor de objetos XAML procesa el uso de una extensión de marcado y llama a <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>, el contexto de cuando era el uso de una extensión de marcado se conserva en el flujo de nodo XAML, pero no en el gráfico de objetos. En el gráfico de objetos, solo se conserva el valor. Si tiene escenarios de diseño u otras razones para conservar el uso de la extensión de marcado original en el resultado serializado, debe diseñar su propia infraestructura para realizar el seguimiento de los usos de la extensión de marcado desde el flujo de nodo XAML de la ruta de acceso de carga. Puede implementar un comportamiento que vuelva a crear los elementos del flujo de nodo a partir de la ruta de acceso de carga y los reproduzca en escritores XAML para la serialización en la ruta de acceso de guardado, sustituyendo el valor en la posición adecuada del flujo de nodo.

## <a name="markup-extensions-in-the-xaml-node-stream"></a>Extensiones de marcado en el flujo de nodo XAML

Si está trabajando con un flujo de nodo XAML en la ruta de acceso de carga, el uso de una extensión de marcado aparece como objeto en el flujo de nodo.

Si el uso de la extensión de marcado usa argumentos posicionales, se representa como un objeto de inicio con un valor de inicialización. Como representación de texto aproximada, el flujo de nodo se parece a lo siguiente:

`StartObject` (<xref:System.Xaml.XamlType> es el tipo de definición de la extensión de marcado, no el tipo de valor devuelto)

`StartMember` (el nombre de <xref:System.Xaml.XamlMember> es `_InitializationText`)

`Value` (el valor son los argumentos posicionales como cadena, incluidos los delimitadores que intervengan)

`EndMember`

`EndObject`

El uso de una extensión de marcado con argumentos con nombre se representa como un objeto con miembros de los nombres correspondientes, cada conjunto de ellos con valores de cadena de texto.

Para invocar realmente la implementación `ProvideValue` de una extensión de marcado se requiere el contexto de esquema XAML, ya que es necesaria la asignación de tipos y la creación de una instancia de tipo de compatibilidad de la extensión de marcado. Esta es una de las razones por las que los usos de la extensión de marcado se conservan de esta forma en los flujos de nodo predeterminados de los servicios XAML de .NET: la parte del lector de una ruta de acceso de carga no suele tener disponible el contexto de esquema XAML necesario.

Si está trabajando con un flujo de nodo XAML en la ruta de acceso de guardado, no suele haber nada en una representación del gráfico de objetos que informe de que el objeto que se va a serializar se proporcionó originalmente mediante el uso de una extensión de marcado y un resultado `ProvideValue` . Los escenarios que necesitan conservar los usos de la extensión de marcado para realizar un recorrido de ida y vuelta y, al mismo tiempo, capturar otros cambios en el gráfico de objetos deben diseñar sus propias técnicas para conservar el conocimiento del uso de una extensión de marcado a partir de la entrada XAML original. Por ejemplo, para restaurar los usos de la extensión de marcado, puede que necesite trabajar con el flujo de nodo en la ruta de acceso de guardado para restaurar los usos de la extensión de marcado, o bien realizar algún tipo de combinación entre el XAML original y el XAML de ida y vuelta. Algunos marcos que implementan XAML, como WPF, usan tipos intermedios (expresiones) para ayudar a representar casos cuando los usos de la extensión de marcado proporcionaron los valores.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Markup.MarkupExtension>
- [Convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions.md)
- [Extensiones de marcado y XAML de WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
