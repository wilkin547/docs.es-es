---
title: Detalles de serialización XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, about XML serialization
- ICollection interface, serializing
- XmlSerializer class, serializing
- serialization, about serialization
- DataSet class, serializing
- XML Schema, serializing
ms.assetid: 8c63200d-db63-4a03-a93d-21641623df62
ms.openlocfilehash: d644e80cbf5ac17fca4df039d915c847a1936217
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588452"
---
# <a name="xml-serialization"></a>serialización XML

La serialización es el proceso de convertir un objeto a un formulario que pueda transportarse fácilmente. Por ejemplo, puede serializar un objeto y transportarlo a través de Internet utilizando http entre un cliente y un servidor. El otro fin para el cual sirve es que la deserialización reconstruye el objeto desde la secuencia.

 La serialización XML serializa solo los campos públicos y los valores de propiedad de un objeto en una secuencia XML. La serialización XML no incluye información de tipo. Por ejemplo, si tiene un objeto **Book** que existe en el espacio de nombres **Library**, no hay garantía de que se deserialice en un objeto del mismo tipo.

> [!NOTE]
> La serialización XML no convierte los métodos, indizadores, campos privados ni propiedades (excepto las colecciones de solo lectura). Para serializar todos los campos y propiedades, tanto públicos como privados, de un objeto, utilice el <xref:System.Runtime.Serialization.DataContractSerializer> en vez de la serialización XML.

 La clase central en serialización XML es la clase <xref:System.Xml.Serialization.XmlSerializer>, y los métodos más importantes de esta clase son **Serialize** y **Deserialize**. <xref:System.Xml.Serialization.XmlSerializer> crea los archivos C# y los compila en archivos .dll para realizar esta serialización. En .NET Framework 2.0, la [herramienta Generador de serializador XML (Sgen.exe)](xml-serializer-generator-tool-sgen-exe.md) está diseñada para generar de antemano estos ensamblados de serialización para implementarlos con la aplicación y mejorar el rendimiento de inicio. La secuencia XML generada por **XmlSerializer** es conforme con la [recomendación del lenguaje de definición de esquema XML (XSD) 1.0](https://www.w3.org/TR/xslt) de World Wide Web Consortium (W3C). Además, los tipos de datos generados son conformes al documento titulado "Esquema XML parte 2: Tipos de datos."

 Los datos de los objetos se describen mediante construcciones de lenguaje de programación, como clases, campos, propiedades, tipos primitivos, matrices e incluso XML insertado en forma de objetos **XmlElement** o **XmlAttribute**. Existe la opción de crear clases propias, anotadas con atributos, o de utilizar la herramienta de definición de esquema XML para generar las clases de acuerdo con un documento de esquema XML existente.

 Si se dispone de un esquema XML, es posible ejecutar la herramienta de definición de esquema XML con el fin de generar un conjunto de clases fuertemente tipadas para el esquema y que se anoten con atributos. Cuando se serializa una instancia de este tipo de clase, el XML generado se adhiere al Esquema XML. Contando con este tipo de clase, se puede programar con un modelo de objetos manipulados con facilidad estando asegurado que el XML generado cumple el esquema XML. Esta es una alternativa al uso de otras clases en .NET Framework, como las clases **XmlReader** y **XmlWriter**, para analizar y escribir una secuencia XML. Para obtener más información, vea [XML Documents and Data](../../../docs/standard/data/xml/index.md) (Documentos y datos XML). Estas clases le permiten analizar cualquier secuencia XML. En contraste, use **XmlSerializer** cuando se espera que la secuencia XML cumpla con un esquema XML conocido.

 Los atributos controlan la secuencia XML generada por la clase **XmlSerializer**, lo que le permite establecer el espacio de nombres XML, el nombre de elemento, el nombre de atributo, etc., de la secuencia XML. Para obtener más información sobre estos atributos y la forma en que controlan la serialización XML, vea [Controlling XML Serialization Using Attributes](controlling-xml-serialization-using-attributes.md) (Controlar la serialización XML mediante atributos). Para consultar una tabla de los atributos que se usan para controlar el XML generado, vea [Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md) (Atributos que controlan la serialización XML).

 La clase **XmlSerializer** puede serializar adicionalmente un objeto y generar una secuencia XML SOAP codificada. El XML generado cumple las normas de la sección 5 del documento de World Wide Web Consortium con título "Protocolo simple de acceso a objetos (SOAP) 1.1" (SOAP). Para más información sobre este proceso, vea [Procedimiento para serializar un objeto como secuencia XML con codificación SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md). Para consultar una tabla de los atributos que controlan el XML generado, vea [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md) (Atributos que controlan la serialización SOAP codificada).

 La clase **XmlSerializer** genera los mensajes SOAP creados por servicios Web XML y pasados a estos. Para controlar los mensajes SOAP, puede aplicar los atributos a las clases, los valores devueltos, parámetros y campos situados en un archivo de servicio Web XML (.asmx). Puede utilizar ambos, los atributos mostrados en "atributos que controlan la serialización XML" y los “atributos que controlan la serialización de SOAP codificada” porque un servicio Web XML puede utilizar o el estilo SOAP literal o codificado. Para obtener más información sobre cómo usar atributos para controlar el XML generado por un servicio Web XML, vea [XML Serialization with XML Web Services](xml-serialization-with-xml-web-services.md) (Serialización XML con servicios Web XML). Para más información sobre SOAP y servicios Web XML, vea [Personalizar el formato de mensajes SOAP](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dkwy2d72(v=vs.100)).

## <a name="security-considerations-for-xmlserializer-applications"></a>Consideraciones de seguridad para aplicaciones XmlSerializer

Si crea una aplicación que usa la clase **XmlSerializer**, conviene estar al tanto de los siguientes puntos y sus implicaciones:

- **XmlSerializer** crea archivos de C# (.cs) y los compila en archivos .dll en el directorio denominado por la variable de entorno TEMP; la serialización se produce con esas DLL.

  > [!NOTE]
  > Estos ensamblados de serialización se pueden generar de antemano y firmar utilizando la herramienta SGen.exe. Esta no es la causa del funcionamiento de ningún servidor de servicio Web. En otras palabras, solo está para el uso del cliente y para la serialización manual.

  El código y las DLL son vulnerables a un proceso malintencionado en el momento de creación y compilación. Al utilizar un equipo que ejecuta Microsoft Windows NT 4.0 o posterior, podría ser posible que dos o más usuarios compartan el directorio TEMP. Es peligroso compartir un directorio TEMP si las dos cuentas tienen privilegios de seguridad diferentes y la cuenta con privilegios más altos ejecuta una aplicación mediante **XmlSerializer**. En este caso, un usuario puede incumplir la seguridad del equipo reemplazando o el archivo .cs o .dll que está compilado. Para eliminar esta preocupación, siempre asegurarse de que cada cuenta en el equipo tiene su propio perfil. De forma predeterminada, la variable de entorno TEMP señala a un directorio diferente para cada cuenta.

- Si un usuario malintencionado envía una secuencia continua de datos XML a un servidor web (un ataque por denegación de servicio), **XmlSerializer** sigue procesando los datos hasta que el equipo se quede sin recursos.

  Este tipo de ataque se elimina si se está utilizando un equipo que ejecuta Internet Information Services (IIS), y su aplicación se está ejecutando dentro de IIS. IIS representa una puerta que no procesa secuencias que sean más largas que la cantidad fija (el valor predeterminado es 4 KB). Si crea una aplicación que no usa IIS y deserializa con **XmlSerializer**, debería implementar una puerta similar que evite un ataque por denegación de servicio.

- **XmlSerializer** serializa los datos y ejecuta código mediante el uso de cualquier tipo que se le dé.

  Hay dos maneras en las que un objeto malintencionado representa una amenaza. Podría ejecutar software malintencionado o insertarlo en el archivo de C# creado por **XmlSerializer**. En el primer caso, si un objeto malintencionado intenta ejecutar un procedimiento destructivo, la seguridad de acceso del código ayuda a evitar que se haga cualquier daño. En el segundo caso, existe la posibilidad de que un objeto malintencionado inserte de algún modo código en el archivo de C# creado por **XmlSerializer**. Aunque se ha examinado este problema completamente, y este tipo de ataque está considerado improbable, debería tomar la precaución de nunca serializar los datos con un tipo desconocido y de poca confianza.

- Los datos confidenciales serializados podrían ser vulnerables.

  Después de que **XmlSerializer** haya serializado los datos, estos pueden almacenarse como un archivo XML u otro almacén de datos. Si su almacén de datos está disponible para otros procesos, o está visible en una intranet o Internet, los datos se pueden robar y utilizar malévolamente. Por ejemplo, si se crea una aplicación que serializa órdenes, que incluyen la tarjeta de crédito, los datos son muy sensibles. Para ayudar a evitar esto, siempre proteja el almacén para que sus datos y los pasos de la toma lo mantenga privado.

## <a name="serialization-of-a-simple-class"></a>Serialización de una clase simple

El ejemplo de código siguiente muestra una clase básica con un campo público.

```vb
Public Class OrderForm
    Public OrderDate As DateTime
End Class
```

```csharp
public class OrderForm
{
    public DateTime OrderDate;
}
```

Cuando se serializa una instancia de esta clase, se podría parecer a lo siguiente.

```xml
<OrderForm>
    <OrderDate>12/12/01</OrderDate>
</OrderForm>
```

Para obtener más ejemplos de serialización, vea [Examples of XML Serialization](examples-of-xml-serialization.md) (Ejemplos de serialización XML).

## <a name="items-that-can-be-serialized"></a>Elementos que se pueden serializar

Los elementos siguientes se pueden serializar mediante la clase **XmLSerializer**:

- Las propiedades de lectura y escritura públicas y campos de clases públicas.

- Las clases que implementan **ICollection** o **IEnumerable**.

  > [!NOTE]
  > Solo se serializan las colecciones, no las propiedades públicas.

- Los objetos **XmlElement**.

- Los objetos **XmlNode**.

- Los objetos **DataSet**.

 Para más información sobre cómo serializar o deserializar objetos, vea [Procedimiento para serializar un objeto](how-to-serialize-an-object.md) y [Procedimiento para deserializar un objeto](how-to-deserialize-an-object.md).

## <a name="advantages-of-using-xml-serialization"></a>Ventajas de utilizar serialización XML

La clase **XmlSerializer** proporciona un control completo y flexible al serializar un objeto como XML. Si está creando un servicio Web XML, puede aplicar atributos que controlan la serialización a las clases y miembros para asegurarse que el resultado de XML cumple con un esquema concreto.

Por ejemplo, **XmlSerializer** permite hacer lo siguiente:

- Especifique si un campo o propiedad debería estar codificada como un atributo o un elemento.

- Especifique un espacio de nombres XML para utilizar.

- Especifique el nombre de un elemento o atributo si un campo o el nombre de propiedad es impropio.

Otra ventaja de serialización XML es que no tiene ninguna restricción en las aplicaciones que desarrolla, con tal de que la secuencia XML que se genera cumpla con un esquema determinado. Imagine un esquema que se utiliza para describir los libros. Representa un título, autor, publicador y un elemento de número ISBN. Puede desarrollar una aplicación que procesa los datos XML como usted desee, por ejemplo, como una orden de libro o como un inventario de libros. En cualquier caso, el único requisito es que la secuencia XML cumple con el esquema del lenguaje de definición de esquemas XML (XSD) especificado.

## <a name="xml-serialization-considerations"></a>Consideraciones de la serialización XML

Al usar la clase **XmlSerializer**, debe tener en cuenta lo siguiente:

- La herramienta Sgen.exe está diseñada expresamente para generar los ensamblados de serialización para rendimiento óptimo.

- Los datos serializados contienen solo los datos mismos y la estructura de sus clases. La identidad del tipo y la información del ensamble no están incluidas.

- Solo se pueden serializar los campos y las propiedades públicas. Las propiedades deben ser de acceso público (métodos get y set). Si debe serializar datos no públicos, use la clase <xref:System.Runtime.Serialization.DataContractSerializer> en lugar de la serialización XML.

- Una clase debe tener un constructor sin parámetros que se vaya a serializar por medio de **XmlSerializer**.

- Los métodos no pueden serializarse.

- **XmlSerializer** puede procesar clases que implementan de manera diferente **IEnumerable** o **ICollection** si cumplen ciertos requisitos, como se indica a continuación.

  Una clase que implementa **IEnumerable** debe implementar un método **Add** público que requiere un solo parámetro. El parámetro del método **Add** debe ser coherente (polimórfico) con el tipo devuelto por la propiedad **IEnumerator.Current** devuelta por el método **GetEnumerator**.

  Una clase que implementa **ICollection** además de **IEnumerable** (como **CollectionBase**) debe tener una propiedad indexada pública **Item** (un indexador en C#) que toma un número entero y debe tener una propiedad pública **Count** de tipo **integer**. El parámetro pasado al método **Add** debe ser del mismo tipo que aquel que devuelve la propiedad **Item**, o una de las bases de dicho tipo.

  Para las clases que implementan **ICollection**, los valores que se van a serializar se recuperan de la propiedad **Item** indexada, en lugar de mediante una llamada a **GetEnumerator**. Además, no se serializan los campos públicos y propiedades, con la excepción de los campos públicos que devuelven otra clase de colección (uno que implemente **ICollection**). Para ver un ejemplo, vea [Examples of XML Serialization](examples-of-xml-serialization.md) (Ejemplos de serialización XML).

## <a name="xsd-data-type-mapping"></a>Asignación de tipo de datos XSD

En el documento de W3C titulado [Esquema XML parte 2: Tipos de datos](https://www.w3.org/TR/xmlschema-2/) se especifican los tipos de datos simples que se pueden usar en un esquema de lenguaje de definición de esquema XML (XSD). Para muchos de estos (por ejemplo, **int** y **decimal**), hay un tipo de datos correspondiente en .NET Framework. Pero algunos tipos de datos XML no tienen un tipo de datos correspondiente en .NET Framework (por ejemplo, el tipo de datos **NMTOKEN**). En casos como este, si usa la [herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md) para generar clases a partir de un esquema, se aplica un atributo adecuado a un miembro de cadena de tipo y su propiedad **DataType** se establee en el nombre del tipo de datos XML. Por ejemplo, si un esquema contiene un elemento denominado "MyToken" con el tipo de datos XML **NMTOKEN**, la clase generada podría contener un miembro, como se muestra en el ejemplo siguiente.

```vb
<XmlElement(DataType:="NMTOKEN")> _
Public MyToken As String
```

```csharp
[XmlElement(DataType = "NMTOKEN")]
public string MyToken;
```

De igual forma, si está creando una clase que debe cumplir un esquema XML (XSD) concreto, debe aplicar el atributo adecuado y establecer su propiedad **DataType** en el nombre del tipo de datos XML deseado.

Para obtener una lista completa de asignaciones de tipo, vea la propiedad **DataType** para cualquiera de las clases de atributos siguientes:

- <xref:System.Xml.Serialization.SoapAttributeAttribute>

- <xref:System.Xml.Serialization.SoapElementAttribute>

- <xref:System.Xml.Serialization.XmlArrayItemAttribute>

- <xref:System.Xml.Serialization.XmlAttributeAttribute>

- <xref:System.Xml.Serialization.XmlElementAttribute>

- <xref:System.Xml.Serialization.XmlRootAttribute>

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.IO.FileStream>
- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- [Serialización binaria](binary-serialization.md)
- [Serialización](index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Ejemplos de serialización XML](examples-of-xml-serialization.md)
- [Cómo: serializar un objeto](how-to-serialize-an-object.md)
- [Cómo: deserializar un objeto](how-to-deserialize-an-object.md)
