---
title: Introducción a las estructuras y conceptos de secuencias de nodo XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML node streams [XAML Services]
- nodes [XAML Services], XAML node stream
- XAML [XAML Services], XAML node streams
ms.assetid: 7c11abec-1075-474c-9d9b-778e5dab21c3
ms.openlocfilehash: b3de3dca029c5e676fc7cdebc7735cfdade0228a
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432861"
---
# <a name="xaml-node-stream-structures-and-concepts"></a>Estructuras y conceptos de flujo de nodo XAML

Los lectores XAML y los escritores XAML implementados en los servicios XAML de .NET se basan en el concepto de diseño de un flujo de nodo XAML. El flujo de nodo XAML es una conceptualización de un conjunto de nodos XAML. En esta conceptualización, un procesador XAML recorre la estructura de las relaciones de nodo en el XAML de cada vez. En todo momento, solo existe un registro o posición actuales en un flujo de nodo XAML abierto, y muchos aspectos de la API informan únicamente sobre la información disponible en esa posición. El nodo actual en un flujo de nodo XAML se puede describir como un objeto, un miembro o un valor. Al tratar XAML como un flujo de nodo XAML, los lectores XAML pueden comunicarse con escritores XAML y habilitar un programa para ver, interactuar o modificar el contenido de un flujo de nodo XAML durante una operación de ruta de acceso de carga o de ruta de acceso de guardado que implica XAML. El diseño de la API de lector y escritor XAML y el concepto de flujo de nodo XAML son <xref:System.Xml.XmlReader> <xref:System.Xml.XmlWriter> similares a los diseños y conceptos de lector y escritor relacionados anteriores, como el modelo de objetos de documento XML (DOM) y las clases y. En este tema se describen los conceptos de flujo de nodo XAML y se describe cómo se puede escribir rutinas que interactúan con las representaciones XAML en el nivel de nodo XAML.

## <a name="loading-xaml-into-a-xaml-reader"></a>Cargar XAML en un lector XAML

La clase base <xref:System.Xaml.XamlReader> no declara una técnica determinada para cargar el XAML inicial en un lector XAML. En su lugar, una clase derivada declara e implementa la técnica de carga, incluidas las características y restricciones generales de su origen de entrada para XAML. Por ejemplo, un <xref:System.Xaml.XamlObjectReader> lee un gráfico de objetos a partir del origen de entrada de un solo objeto que representa la raíz o la base. A continuación, el <xref:System.Xaml.XamlObjectReader> genera un flujo de nodo XAML a partir del gráfico de objeto.

La subclase definida por <xref:System.Xaml.XamlReader> servicios XAML <xref:System.Xaml.XamlXmlReader>de .NET más prominente es . <xref:System.Xaml.XamlXmlReader> carga el XAML inicial, ya sea mediante la carga de un archivo de texto directamente a través de una ruta de acceso de archivo o flujo, o indirectamente a través de una clase de lector relacionada, como <xref:System.IO.TextReader>. Puede considerarse que el <xref:System.Xaml.XamlReader> contiene la totalidad del origen de entrada de XAML después de cargarse. Sin embargo, la API base de <xref:System.Xaml.XamlReader> está diseñada para que el lector interactúe con un único nodo del XAML. Cuando se carga por primera vez, el primer nodo único que encuentra es la raíz de XAML y su objeto de inicio.

### <a name="the-xaml-node-stream-concept"></a>El concepto de flujo de nodo XAML

Si está más familiarizado con un DOM, una metáfora de árbol o un enfoque basado en consultas para obtener acceso a tecnologías basadas en XML, una forma útil de conceptualizar un flujo de nodo XAML es la siguiente. Imagine que el XAML cargado es un DOM o un árbol donde todos los nodos posibles se expanden por completo y, a continuación, se presentan linealmente. A medida que avanza a través de los nodos, puede recorrer «hacia dentro» o «hacia fuera» los niveles que son pertinentes para un DOM, pero el flujo de nodo XAML no realiza un seguimiento explícitamente, ya que estos conceptos no son relevantes para un flujo de nodo. El flujo de nodo tiene una posición «actual», pero a menos que haya almacenado por su cuenta otras partes del flujo como referencias, no estará a la vista ningún aspecto del flujo de nodo que no sea la posición del nodo actual.

El concepto de flujo de nodo XAML tiene la importante ventaja de que, si recorre todo el flujo de nodo, se asegura de que se ha procesado la representación de XAML al completo; no es necesario preocuparse de si una consulta, una operación DOM u otro enfoque no lineal para el procesamiento de la información perdió alguna parte de la representación XAML completa. Por este motivo, la representación del flujo de nodo XAML es ideal no solo para conectar los lectores y escritores de XAML, sino para proporcionar un sistema donde puede insertar su propio proceso, que actúe entre las fases de lectura y escritura de una operación de procesamiento de XAML. En muchos casos, los lectores de XAML optimizan o reordenan deliberadamente el orden de los nodos del flujo de nodos XAML con respecto a cómo aparecerían en el texto de origen, binario o gráfico de objetos. Este comportamiento está diseñado para aplicar una arquitectura de procesamiento de XAML mediante la cual los escritores de XAML nunca están en una posición en la que tengan que ir hacia «atrás» en el flujo de nodo. Idealmente, todas las operaciones de escritura XAML debe poder actuar en función del contexto de esquema y la posición actual del flujo de nodos.

## <a name="a-basic-reading-node-loop"></a>Un bucle de nodo de lectura básico

Un bucle de nodo de lectura básico para examinar un flujo de nodo XAML se compone de los siguientes conceptos. A los efectos de los bucles de nodo tal como se describen en este tema, suponga que está leyendo un archivo XAML basado en texto y en lenguaje natural mediante <xref:System.Xaml.XamlXmlReader>. Los vínculos de esta sección hacen referencia a la API de bucle de nodo XAML específica implementada por <xref:System.Xaml.XamlXmlReader>.

- Asegúrese de que no está al final del flujo de nodo XAML (consulte <xref:System.Xaml.XamlXmlReader.IsEof%2A>o use el <xref:System.Xaml.XamlXmlReader.Read%2A> valor devuelto). Si está al final del flujo, no hay ningún nodo actual y debe salir.

- Compruebe qué tipo de nodo del flujo de nodo XAML se expone actualmente mediante una llamada a <xref:System.Xaml.XamlXmlReader.NodeType%2A>.

- Si tiene un escritor de objetos XAML asociado que esté directamente conectado, lo habitual es llamar a <xref:System.Xaml.XamlWriter.WriteNode%2A> en este momento.

- En función del <xref:System.Xaml.XamlNodeType> que se notifique como nodo actual o registro actual, haga una de las siguientes llamadas para obtener información sobre el contenido del nodo:

  - Para un <xref:System.Xaml.XamlXmlReader.NodeType%2A> de <xref:System.Xaml.XamlNodeType.StartMember> o <xref:System.Xaml.XamlNodeType.EndMember>, llame a <xref:System.Xaml.XamlXmlReader.Member%2A> para obtener información <xref:System.Xaml.XamlMember> sobre un miembro. El miembro puede <xref:System.Xaml.XamlDirective>ser un , y por lo tanto no necesariamente podría ser un miembro definido por tipo convencional del objeto anterior. Por ejemplo, `x:Name` aplicado a un objeto aparece como un miembro XAML donde <xref:System.Xaml.XamlMember.IsDirective%2A> es true y el <xref:System.Xaml.XamlMember.Name%2A> del miembro es `Name`, con otras propiedades que indican que esta directiva está bajo el espacio de nombres XAML del lenguaje XAML.

  - Para un <xref:System.Xaml.XamlXmlReader.NodeType%2A> de <xref:System.Xaml.XamlNodeType.StartObject> o <xref:System.Xaml.XamlNodeType.EndObject>, llame a <xref:System.Xaml.XamlXmlReader.Type%2A> para obtener información <xref:System.Xaml.XamlType> sobre un objeto.

  - Para un <xref:System.Xaml.XamlXmlReader.NodeType%2A> de <xref:System.Xaml.XamlNodeType.Value>, llame a <xref:System.Xaml.XamlXmlReader.Value%2A>. Un nodo es un valor si es la expresión más simple de un valor para un miembro, o el texto de inicialización de un objeto (sin embargo, debe tener en cuenta el comportamiento de conversión de tipos, tal como se describe en una sección posterior de este tema).

  - Para un <xref:System.Xaml.XamlXmlReader.NodeType%2A> de <xref:System.Xaml.XamlNodeType.NamespaceDeclaration>, llame a <xref:System.Xaml.XamlXmlReader.Namespace%2A> para obtener información de espacio de nombres para un nodo de espacio de nombres.

- Llame a <xref:System.Xaml.XamlXmlReader.Read%2A> para avanzar el lector XAML al nodo siguiente en el flujo de nodo XAML, y vuelva a repetir los pasos.

El flujo de nodo XAML proporcionado por los lectores XAML de Servicios XAML de .NET siempre proporciona un recorrido completo y profundo de todos los nodos posibles. Las técnicas de control de flujo típicas para un bucle de nodo XAML incluyen definir un cuerpo dentro de `while (reader.Read())`y activar <xref:System.Xaml.XamlXmlReader.NodeType%2A> en cada punto de nodo en el bucle de nodo.

Si el flujo de nodo está al final del archivo, el nodo actual es null.

El bucle más sencillo que usa un lector y un escritor es similar al siguiente ejemplo.

```csharp
XamlXmlReader xxr = new XamlXmlReader(new StringReader(xamlStringToLoad));
//where xamlStringToLoad is a string of well formed XAML
XamlObjectWriter xow = new XamlObjectWriter(xxr.SchemaContext);
while (xxr.Read()) {
  xow.WriteNode(xxr);
}
```

Este ejemplo básico de un bucle de nodo XAML de ruta de acceso de carga conecta de forma transparente el lector XAML y el escritor XAML, sin hacer nada diferente que si hubiera usado <xref:System.Xaml.XamlServices.Parse%2A?displayProperty=nameWithType>. Pero, a continuación, esta estructura básica se expande para aplicarse a su escenario de escritura o lectura. Algunos escenarios posibles son los siguientes:

- Active <xref:System.Xaml.XamlXmlReader.NodeType%2A>. Realice diferentes acciones en función de qué tipo de nodo se está leyendo.

- No llame a <xref:System.Xaml.XamlWriter.WriteNode%2A> en todos los casos. Solo llame a <xref:System.Xaml.XamlWriter.WriteNode%2A> en algunos casos de <xref:System.Xaml.XamlXmlReader.NodeType%2A> .

- Dentro de la lógica de un tipo de nodo determinado, analice las características concretas de ese nodo y actúe sobre ellas. Por ejemplo, solo podría escribir objetos que provengan de un espacio de nombres XAML determinado y, a continuación, quitar o aplazar cualquier objeto que no provenga de ese espacio de nombres XAML. También podría anular o reprocesar de otro modo las directivas XAML que su sistema XAML no admita como parte de su procesamiento del miembro.

- Defina un <xref:System.Xaml.XamlObjectWriter> personalizado que invalide los métodos `Write*` , posiblemente realizando la asignación de tipos que omite el contexto de esquema XAML.

- Construya el <xref:System.Xaml.XamlXmlReader> de modo que use un contexto de esquema XAML no predeterminado, para que el lector y el escritor usen las diferencias personalizadas en el comportamiento XAML.

### <a name="accessing-xaml-beyond-the-node-loop-concept"></a>Acceder a XAML más allá del concepto de bucle de nodo

Existen otras maneras de trabajar con una representación de XAML, además del bucle de nodo XAML. Por ejemplo, podría existir un lector XAML que puede leer un nodo indexado o en concreto acceder a los nodos directamente a través de `x:Name`, `x:Uid`u otros identificadores. Los servicios XAML de .NET no proporcionan una implementación completa, pero proporciona un patrón sugerido a través de servicios y tipos de soporte técnico. Para más información, vea <xref:System.Xaml.IXamlIndexingReader> y <xref:System.Xaml.XamlNodeList>.

## <a name="working-with-the-current-node"></a>Trabajar con el nodo actual

La mayoría de los escenarios que usan un bucle de nodo XAML no leen solo los nodos. La mayoría de los escenarios procesan los nodos actuales y pasan cada nodo de uno en uno a una implementación de <xref:System.Xaml.XamlWriter>.

En el escenario típico de ruta de acceso de carga, un <xref:System.Xaml.XamlXmlReader> genera un flujo de nodo XAML; los nodos XAML se procesan según su lógica y su contexto de esquema XAML; y los nodos se pasan a un <xref:System.Xaml.XamlObjectWriter>. A continuación, integre el gráfico de objetos resultante en su aplicación o marco.

En un escenario típico de ruta de acceso de guardado, un <xref:System.Xaml.XamlObjectReader> lee el gráfico de objetos, se procesan los nodos XAML individuales y un <xref:System.Xaml.XamlXmlWriter> genera el resultado serializado como un archivo de texto XAML. La clave es que tanto las rutas de acceso como los escenarios implican trabajar exactamente con un nodo XAML a la vez y los nodos XAML están disponibles para el tratamiento de forma estandarizada definida por el sistema de tipos XAML y the.NET API de servicios XAML.

### <a name="frames-and-scope"></a>Marcos y ámbito

Un bucle de nodo XAML le guía a través de un flujo de nodo XAML de manera lineal. El flujo de nodo recorre los objetos, los miembros que contienen otros objetos y así sucesivamente. A menudo resulta útil realizar un seguimiento del ámbito dentro del flujo de nodo XAML implementando un concepto de marco de pila. Esto es especialmente cierto si está ajustando activamente el flujo de nodo mientras está en él. La compatibilidad de marco de pila que implemente como parte de la lógica de bucle de nodo puede contar ámbitos `StartObject` (o `GetObject`) y `EndObject` a medida que desciende en una estructura de nodo XAML, si la estructura se considera desde una perspectiva de DOM.

## <a name="traversing-and-entering-object-nodes"></a>Atravesar y escribir nodos de objeto

El primer nodo de un flujo de nodos cuando se abre un lector de XAML es el nodo de objeto de inicio del objeto raíz. Por definición, este objeto siempre es un nodo de objeto único y no tiene ningún nodo del mismo nivel. En cualquier ejemplo de XAML real, el objeto raíz se define de modo que tenga una o varias propiedades que contienen más objetos, y estas propiedades tienen nodos de miembro. Los nodos de miembro tienen uno o más nodos de objeto, o en su lugar también pueden terminar en un nodo de valor. El objeto raíz suele definir los ámbitos de nombres XAML, que sintácticamente se asignan como atributos en el marcado de texto XAML, pero se asignan a un tipo de nodo `Namescope` en la representación del flujo de nodo XAML.

Considere el siguiente ejemplo XAML (esto es XAML arbitrario, no respaldado por tipos existentes en .NET). Suponga que en este modelo de objetos, `FavorCollection` es `List<T>` de `Favor`, `Balloon` y `NoiseMaker` son asignables a `Favor`, la propiedad `Balloon.Color` está respaldada por un objeto `Color` similar a la forma en que WPF define los colores como nombres de colores conocidos, y `Color` admite un convertidor de tipos para la sintaxis de atributo.

|Marcado XAML|Flujo de nodo XAML resultante|
|-----------------|--------------------------------|
|`<Party`|`Namespace` para `Party`|
|`xmlns="PartyXamlNamespace">`|`StartObject` para `Party`|
|`<Party.Favors>`|`StartMember` para `Party.Favors`|
||Nodo`StartObject` para la `FavorCollection`implícita|
||Nodo`StartMember` para la propiedad Items `FavorCollection` implícita|
|`<Balloon`|`StartObject` para `Balloon`|
|`Color="Red"`|`StartMember` para `Color`<br /><br /> `Value` para la cadena de valor de atributo `"Red"`<br /><br /> `EndMember` para `Color`|
|`HasHelium="True"`|`StartMember` para `HasHelium`<br /><br /> `Value` para la cadena de valor de atributo `"True"`<br /><br /> `EndMember` para `HasHelium`|
|`>`|`EndObject` para `Balloon`|
|`<NoiseMaker>Loudest</NoiseMaker>`|`StartObject` para `NoiseMaker`<br /><br /> `StartMember` para `_Initialization`<br /><br /> `Value` para la cadena de valor de inicialización `"Loudest"`<br /><br /> `EndMember` para `_Initialization`<br /><br /> `EndObject` para `NoiseMaker`|
||Nodo`EndMember` para la propiedad Items `FavorCollection` implícita|
||Nodo`EndObject` para la `FavorCollection`implícita|
|`</Party.Favors>`|`EndMember` para `Favors`|
|`</Party>`|`EndObject` para `Party`|

En el flujo de nodo XAML, puede confiar en el comportamiento siguiente:

- Si existe un nodo `Namespace` , se agrega al flujo inmediatamente antes del `StartObject` que declaró el espacio de nombres XAML con `xmlns`. Vuelva a consultar la tabla anterior con el XAML y el flujo de nodo de ejemplo. Observe que los nodos `StartObject` y `Namespace` parecen estar transpuestos con respecto a sus posiciones de declaración en el marcado de texto. Esto es representativo del comportamiento donde los nodos de espacios de nombres siempre aparecen antes que el nodo al que se aplican en el flujo de nodos. Este diseño se debe a que la información del espacio de nombres es vital para los escritores de objetos y debe conocerse antes de que el escritor de objetos intente realizar una asignación de tipos o procesar de otra manera el objeto. Si se coloca la información del espacio de nombres XAML delante de su ámbito de aplicación en el flujo, es más fácil procesar el flujo de nodo en el orden presentado.

- Debido a la consideración anterior, en la mayoría de los casos de marcado reales, lo primero que se lee es uno o más nodos `Namespace` al atravesar los nodos desde el principio, no el `StartObject` de la raíz.

- Un nodo `StartObject` puede ir seguido de un `StartMember`, un `Value`o un `EndObject`inmediato. Nunca va inmediatamente seguido de otro `StartObject`.

- Un `StartMember` puede ir seguido de un `StartObject`, un `Value`o un `EndMember`inmediato. Puede ir seguido de un `GetObject`, para los miembros en los que se supone que el valor procede de un valor existente del objeto primario, en lugar de un `StartObject` que crearía una instancia de un nuevo valor. También puede ir seguido de un nodo `Namespace` , que se aplica a un próximo `StartObject`. Nunca va inmediatamente seguido de otro `StartMember`.

- Un nodo `Value` representa el propio valor; no hay ningún «EndValue». Solo puede ir seguido de un `EndMember`.

  - El texto de inicialización de XAML del objeto, tal y como puede usarlo la construcción, no da como resultado una estructura Objeto-Valor. En su lugar, se crea un nodo de miembro dedicado para un miembro denominado `_Initialization` y ese nodo de miembro contiene la cadena de valor de inicialización. Si existe, `_Initialization` siempre es el primer `StartMember`. `_Initialization` se puede calificar en algunas representaciones de servicios XAML con el ámbito de nombres XAML del lenguaje XAML, para aclarar que `_Initialization` no es una propiedad definida en los tipos de respaldo.

  - Una combinación Miembro-Valor representa la configuración de atributo del valor. Finalmente podría haber un convertidor de valores implicado en el procesamiento de este valor, y el valor es una cadena sin formato. Sin embargo, esto no se evalúa hasta que un escritor de objetos XAML procesa este flujo de nodo. El escritor de objetos XAML posee el contexto de esquema XAML, la asignación del sistema de tipos y otras compatibilidades que son necesarios para las conversiones de valores.

- Un nodo `EndMember` puede ir seguido de un nodo `StartMember` para un miembro subsiguiente, o bien de un nodo `EndObject` para el propietario del miembro.

- Un nodo `EndObject` puede ir seguido de un nodo `EndMember` . También puede ir seguido de un nodo `StartObject` para los casos en que los objetos sean del mismo nivel en los elementos de la colección. Asimismo, puede ir seguido de un nodo `Namespace` , que se aplica a un próximo `StartObject`.

  - Para el caso único de cerrar el flujo de nodo completo, el `EndObject` de la raíz no va seguido de nada; el lector es ahora el final del archivo y <xref:System.Xaml.XamlReader.Read%2A> devuelve `false`.

## <a name="value-converters-and-the-xaml-node-stream"></a>Convertidores de valores y flujo de nodo XAML

Un convertidor de valores es un término general para referirse a una extensión de marcado, un convertidor de tipos (incluidos los serializadores de valores) u otra clase dedicada que se notifica como un convertidor de valores a través del sistema de tipos XAML. En el flujo de nodo XAML, el uso de un convertidor de tipos y el uso de una extensión de marcado tienen representaciones muy diferentes.

### <a name="type-converters-in-the-xaml-node-stream"></a>Convertidores de tipos en el flujo de nodo XAML

Un conjunto de atributos que finalmente tiene como resultado un uso del convertidor de tipos se notifica en el flujo de nodo XAML como un valor de un miembro. El flujo de nodo XAML no intenta generar un objeto de instancia del convertidor de tipos y pasarle el valor. El uso de la implementación de conversión de un convertidor de tipos requiere invocar el contexto de esquema XAML y usarlo para la asignación de tipos. Incluso el proceso de determinar qué clase de convertidor de tipos se debería usar para procesar el valor requiere indirectamente el contexto de esquema XAML. Cuando se usa el contexto de esquema XAML predeterminado, esa información está disponible en el sistema de tipos XAML. Si necesita información sobre la clase del convertidor de tipos en el nivel de flujo de nodo XAML antes de la conexión a un escritor de XAML, puede obtenerla en la información <xref:System.Xaml.XamlMember> del miembro que se va a establecer. Pero de lo contrario, la entrada del convertidor de tipos debe conservarse en el flujo de nodo XAML como un valor sin formato hasta que se realicen el resto de operaciones que requieren el sistema de asignación de tipos y el contexto de esquema XAML, por ejemplo, la creación de objetos por un escritor de objetos XAML.

Por ejemplo, considere el siguiente esquema de definición de clase y el uso XAML para dicho esquema:

```csharp
public class BoardSizeConverter : TypeConverter {
  //converts from string to an int[2] by splitting on an "x" char
}
public class GameBoard {
  [TypeConverter(typeof(BoardSizeConverter))]
  public int[] BoardSize; //2x2 array, initialization not shown
}
```

```xaml
<GameBoard BoardSize="8x8"/>
```

Una representación de texto del flujo de nodo XAML para este uso se puede expresar de la siguiente manera:

`StartObject` con <xref:System.Xaml.XamlType> que representa `GameBoard`

`StartMember` con <xref:System.Xaml.XamlMember> que representa `BoardSize`

Nodo`Value` con la cadena de texto «`8x8`»

`EndMember` coincide con `BoardSize`

`EndObject` coincide con `GameBoard`

Observe que no hay ninguna instancia del convertidor de tipos en este flujo de nodo. Sin embargo, puede obtener información del convertidor de tipos llamando a <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> en el <xref:System.Xaml.XamlMember> para `BoardSize`. Si tiene un contexto de esquema XAML válido, también puede invocar los métodos de convertidor obteniendo una instancia de <xref:System.Xaml.Schema.XamlValueConverter%601.ConverterInstance%2A>.

### <a name="markup-extensions-in-the-xaml-node-stream"></a>Extensiones de marcado en el flujo de nodo XAML

El uso de una extensión de marcado se notifica en el flujo de nodo XAML como un nodo de objeto dentro de un miembro, donde el objeto representa una instancia de la extensión de marcado. Por lo tanto, el uso de una extensión de marcado se presenta más explícitamente en la representación del flujo de nodo que el uso de un convertidor de tipos, y contiene más información. La información de<xref:System.Xaml.XamlMember> podría no mencionar nada sobre la extensión de marcado, ya que el uso es situacional y varía en cada caso de marcado posible; no es dedicado ni implícito por tipo o miembro, como es el caso de los convertidores de tipos.

La representación del flujo de nodo de las extensiones de marcado como nodos de objeto es el caso incluso si el uso de la extensión de marcado se realizó en forma de atributo en el marcado de texto XAML (que suele ser el caso). Los usos de la extensión de marcado que utilizaron un formulario de elemento de objeto explícito se tratan del mismo modo.

Dentro de un nodo de objeto de extensión de marcado, puede haber miembros de esa extensión de marcado. La representación del flujo de nodo XAML conserva el uso de esa extensión de marcado, ya sea un uso de parámetro posicional o un uso con parámetros con nombre explícitos.

Para un uso de parámetro posicional, el flujo de nodo XAML contiene una propiedad `_PositionalParameters` definida por el lenguaje XAML que graba el uso. Esta propiedad es una <xref:System.Collections.Generic.List%601> genérica con una restricción <xref:System.Object> . La restricción es un objeto y no una cadena, ya que cabe la posibilidad de que el uso de un parámetro posicional contenga los usos de la extensión de marcado anidados dentro de él. Para acceder a los parámetros posicionales desde el uso, puede iterar en la lista y usar los indizadores para los valores de lista individuales.

Para un uso de parámetro con nombre, cada parámetro con nombre se representa como un nodo de miembro de ese nombre en el flujo de nodos. Los valores de miembro no son necesariamente cadenas, ya que podría haber un uso de una extensión de marcado anidado.

Todavía no se invoca`ProvideValue` en el marcado de extensión. Sin embargo, se invoca si conecta un lector de XAML y el escritor de XAML para que se invoque `WriteEndObject` en el nodo de la extensión de marcado cuando lo examina el flujo de nodo. Por esta razón, normalmente necesitará que esté disponible el mismo contexto de esquema XAML que se usaría para formar el gráfico de objetos en la ruta de acceso de carga. De lo contrario, el `ProvideValue` de cualquier extensión de marcado puede producir excepciones aquí, ya que no tiene a su disposición los servicios esperados.

## <a name="xaml-and-xml-language-defined-members-in-the-xaml-node-stream"></a>Miembros definidos por el lenguaje XAML y XML en el flujo de nodo XAML

Ciertos miembros se introducen en un flujo de nodos XAML debido a las interpretaciones y las convenciones de un lector de XAML, en lugar de a través de una búsqueda o construcción de <xref:System.Xaml.XamlMember> explícitas. A menudo, estos miembros son directivas XAML. En algunos casos, es el hecho de leer el XAML lo que introduce la directiva en el flujo de nodos XAML. En otras palabras, el texto XAML de entrada original no especificaba explícitamente la directiva miembro, pero el lector XAML inserta la directiva para satisfacer una convención XAML estructural y la información de informe en el flujo de nodo XAML antes de que se pierda esa información.

En la lista siguiente se indican todos los casos en los que se espera que un lector XAML introduzca un nodo miembro XAML de directiva y cómo se identifica ese nodo miembro en las implementaciones de servicios XAML de .NET.

- **Texto de inicialización para un nodo de objeto:** el nombre de este nodo de miembro es `_Initialization`. Representa una directiva XAML y se define en el espacio de nombres XAML del lenguaje XAML. Puede obtener una entidad estática desde <xref:System.Xaml.XamlLanguage.Initialization%2A>.

- **Parámetros posicionales para una extensión de marcado:** el nombre de este nodo de miembro es `_PositionalParameters`, y se define en el espacio de nombres XAML del lenguaje XAML. Siempre contiene una lista genérica de objetos, cada uno de los cuales es un parámetro posicional separado previamente dividiendo en el carácter delimitador de `,` , tal como se suministra en el XAML de entrada. Puede obtener una entidad estática para la directiva de parámetros posicionales de <xref:System.Xaml.XamlLanguage.PositionalParameters%2A>.

- **Contenido desconocido:** el nombre de este nodo de miembro es `_UnknownContent`. En realidad, es una <xref:System.Xaml.XamlDirective>, y se define en el espacio de nombres XAML del lenguaje XAML. Esta directiva se usa como centinela para los casos en que un elemento de objeto XAML incluye contenido en el XAML de origen, pero no puede determinarse ninguna propiedad de contenido en el contexto de esquema XAML que está disponible actualmente. Puede detectar este caso en un flujo de nodo XAML buscando los miembros denominados `_UnknownContent`. Si no se realiza ninguna otra acción en un flujo de nodo XAML de ruta de acceso de carga, se produce el valor predeterminado <xref:System.Xaml.XamlObjectWriter> en un intento de `WriteEndObject` cuando encuentra el miembro `_UnknownContent` en cualquier objeto. El valor predeterminado <xref:System.Xaml.XamlXmlWriter> no se produce y trata el miembro como implícito. Puede obtener una entidad estática para `_UnknownContent` desde <xref:System.Xaml.XamlLanguage.UnknownContent%2A>.

- **Propiedad Collection de una colección:** Aunque el tipo CLR de respaldo de una clase de colección que se usa para XAML normalmente tiene una propiedad con nombre dedicada que contiene los elementos de colección, esa propiedad no es conocida por un sistema de tipos XAML antes de la resolución de tipos de respaldo. En su lugar, el flujo de nodo XAML introduce un marcador de posición `Items` como miembro del tipo XAML de la colección. En la implementación de servicios XAML de .NET, el `_Items`nombre de esta directiva o miembro en el flujo de nodo es . Puede obtenerse una constante para esta directiva a partir de <xref:System.Xaml.XamlLanguage.Items%2A>.

    Tenga en cuenta que un flujo de nodo XAML puede contener una propiedad Items con elementos que resultan no ser analizables en función de la resolución de tipos de respaldo y el contexto de esquema XAML. Por ejemplo,

- **Miembros definidos por XML:** El definido `xml:base`XML `xml:lang` `xml:space` y los miembros se `base` `lang`notifican `space` como directivas XAML denominadas , , y en las implementaciones de servicios XAML de .NET. Su espacio de nombres es el espacio de nombres XML `http://www.w3.org/XML/1998/namespace`. Pueden obtenerse constantes para cada uno de ellos a partir de <xref:System.Xaml.XamlLanguage>.

## <a name="node-order"></a>Orden de los nodos

En algunos casos, <xref:System.Xaml.XamlXmlReader> cambia el orden de los nodos XAML en el flujo de nodo XAML, con respecto al orden en que aparecen los nodos si se vieran en el marcado o si se procesaran como XML. La finalidad es ordenar los nodos de modo que un <xref:System.Xaml.XamlObjectWriter> pueda procesar el flujo de nodos en modo de solo avance.  En los servicios XAML de .NET, el lector XAML reordena los nodos en lugar de dejar esta tarea al escritor XAML, como una optimización del rendimiento para los consumidores de escritores de objetos XAML del flujo de nodos.

Determinadas directivas están diseñadas específicamente para proporcionar más información para la creación de un objeto a partir de un elemento de objeto. Estas directivas son `Initialization`, `PositionalParameters`, `TypeArguments`, `FactoryMethod`y `Arguments`. Los lectores XAML de servicios XAML de .NET intentan colocar estas directivas `StartObject`como los primeros miembros en el flujo de nodo después de un objeto, por motivos que se explican en la sección siguiente.

### <a name="xamlobjectwriter-behavior-and-node-order"></a>Comportamiento de XamlObjectWriter y orden de los nodos

El`StartObject` de un <xref:System.Xaml.XamlObjectWriter> no es necesariamente una señal para que el escritor de objetos XAML construya inmediatamente la instancia del objeto. XAML incluye varias características de lenguaje que permiten inicializar un objeto con entrada adicional y no depender por completo de invocar un constructor sin parámetros para generar el objeto inicial y solo entonces establecer propiedades. Estas características incluyen: <xref:System.Windows.Markup.XamlDeferLoadAttribute>; texto de inicialización; [x:TypeArguments](xtypearguments-directive.md); parámetros posicionales de una extensión de marcado; métodos de generador y nodos [x:Arguments](xarguments-directive.md) asociados (XAML 2009). Cada uno de estos casos retrasa la construcción real del objeto y, dado que el flujo de nodo se reordena, el escritor de objetos XAML puede basarse en un comportamiento de construcción efectiva de la instancia siempre que se encuentre un miembro de inicio que no sea específicamente una directiva de construcción para ese tipo de objeto.

### <a name="getobject"></a>GetObject

`GetObject` representa un nodo XAML donde, en lugar de construir un objeto nuevo, un escritor de objetos XAML obtiene el valor de la propiedad que contiene el objeto. Un caso típico en el que se encuentra un nodo `GetObject` en un flujo de nodo XAML es para un objeto de colección o un objeto de diccionario, cuando la propiedad que lo contiene es deliberadamente de solo lectura en el modelo de objeto del tipo de respaldo. En este escenario, la colección o el diccionario suelen crearse e inicializarse (normalmente vacíos) mediante la lógica de inicialización de un tipo de propiedad.

## <a name="see-also"></a>Consulte también

- <xref:System.Xaml.XamlObjectReader>
- [Servicios XAML](index.md)
- [Espacios de nombres XAML](namespaces.md)
