---
title: "Introducir la serializaci&#243;n XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "DataSet (clase), serializar"
  - "ICollection (interfaz), serializar"
  - "serialización, acerca de la serialización"
  - "esquema XML, serializar"
  - "serialización XML, acerca de la serialización XML"
  - "XmlSerializer (clase), serializar"
ms.assetid: 8c63200d-db63-4a03-a93d-21641623df62
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Introducir la serializaci&#243;n XML
La serialización es el proceso de convertir un objeto a un formulario que pueda transportarse fácilmente.Por ejemplo, puede serializar un objeto y transportarlo a través de Internet utilizando http entre un cliente y un servidor.El otro fin para el cual sirve es que la deserialización reconstruye el objeto desde la secuencia.  
  
 La serialización XML serializa solo los campos públicos y los valores de propiedad de un objeto en una secuencia XML.La serialización XML no incluye información de tipo.Por ejemplo, si tiene un objeto **Book** que existe en el espacio de nombres **Library**, no hay ninguna garantía que se deserialice en un objeto del mismo tipo.  
  
> [!NOTE]
>  La serialización XML no convierte los métodos, indizadores, campos privados ni propiedades \(excepto las colecciones de solo lectura\).Para serializar todos los campos y propiedades, tanto públicos como privados, de un objeto, utilice el <xref:System.Runtime.Serialization.DataContractSerializer> en vez de la serialización XML.  
  
 La clase central en serialización XML es la clase [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) y los métodos más importantes en esta clase son **Serialize** y los métodos **Deserialize**.<xref:System.Xml.Serialization.XmlSerializer> crea los archivos C\# y los compila en archivos .dll para realizar esta serialización.En .NET Framework 2.0, [Herramienta Generador de serializador XML \(Sgen.exe\)](../../../docs/framework/serialization/xml-serializer-generator-tool-sgen-exe.md) está diseñada para generar de antemano estos ensamblados de serialización a ser implementados con su aplicación y mejorar el rendimiento de inicio.La secuencia XML generada por **XmlSerializer** es conforme al lenguaje de definición de esquemas XML de World Wide Web Consortium \(XSD\) \(www.w3.org\) 1.0 recomendación.Además, los tipos de datos generados son conformes al documento titulado "Esquema XML parte 2: Tipos de datos."  
  
 Los datos de los objetos se describen utilizando construcciones de lenguaje de programación como, por ejemplo, clases, campos, propiedades, tipos primitivos, matrices e incluso XML incrustado en forma de objetos **XmlElement** o **XmlAttribute**.Existe la opción de crear clases propias, anotadas con atributos, o de utilizar la herramienta de definición de esquema XML para generar las clases de acuerdo con un documento de esquema XML existente.  
  
 Si se dispone de un esquema XML, es posible ejecutar la herramienta de definición de esquema XML con el fin de generar un conjunto de clases fuertemente tipadas para el esquema y que se anoten con atributos.Cuando se serializa una instancia de este tipo de clase, el XML generado se adhiere al Esquema XML.Contando con este tipo de clase, se puede programar con un modelo de objetos manipulados con facilidad estando asegurado que el XML generado cumple el esquema XML.Ésta es una alternativa a utilizar otras clases en .NET Framework, como **XmlReader** y las clases **XmlWriter**, para analizar y escribir una secuencia XML.Para obtener más información, vea [Documentos y datos XML](../../../docs/standard/data/xml/index.md).Estas clases le permiten analizar cualquier secuencia XML.En contraste, utilice **XmlSerializer** cuando se espera que la secuencia XML cumpla con un esquema XML conocido.  
  
 Los atributos controlan la secuencia XML generada por la clase **XmlSerializer**, permitiéndole establecer el espacio de nombres XML, nombre de elemento, el nombre de atributo, etc., de la secuencia XML.Para obtener más información sobre estos atributos y cómo controlan la serialización de XML consulte [Controlar la serialización XML mediante atributos](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md).Para una tabla de esos atributos que se utilizan para controlar el XML generado, vea [Atributos que controlan la serialización XML](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md).  
  
 La clase **XmlSerializer** puede serializar adicionalmente un objeto y generar una secuencia XML SOAP codificada.El XML generado cumple las normas de la sección 5 del documento de World Wide Web Consortium con título "Protocolo simple de acceso a objetos \(SOAP\) 1.1" \(SOAP\). Para obtener más información sobre este proceso, vea [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md).Para una tabla de esos atributos que se utilizan para controlar el XML generado, vea [Atributos que controlan la serialización SOAP codificada](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 La clase **XmlSerializer** genera los mensajes SOAP creados por, y pasados a, Servicios Web XML.Para controlar los mensajes SOAP, puede aplicar los atributos a las clases, los valores devueltos, parámetros y campos situados en un archivo de servicio Web XML \(.asmx\).Puede utilizar ambos, los atributos mostrados en "atributos que controlan la serialización XML" y los “atributos que controlan la serialización de SOAP codificada” porque un servicio Web XML puede utilizar o el estilo SOAP literal o codificado.Para obtener más información sobre cómo utilizar los atributos para controlar el XML generado por un servicio Web XML, vea [Serialización XML con servicios web XML](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md).Para obtener más información acerca de SOAP y Servicios Web XML vea [Customizing SOAP Messages](http://msdn.microsoft.com/es-es/1d777288-c0d9-4e6a-b638-f010da031952).  
  
## Consideraciones de seguridad para aplicaciones XmlSerializer  
 Cuando cree una aplicación que utilice **XmlSerializer**, deberá ser consciente de los elementos siguientes y sus implicaciones:  
  
-   **XmlSerializer** crea los archivos C\# \(.cs\) y los compila en archivos .dll en el directorio denominado por la variable de entorno TEMP; la serialización se produce con esas DLL.  
  
    > [!NOTE]
    >  Estos ensamblados de serialización se pueden generar de antemano y firmar utilizando la herramienta SGen.exe.Esta no es la causa del funcionamiento de ningún servidor de servicio Web.En otras palabras, solo está para el uso del cliente y para la serialización manual.  
  
     El código y las DLL son vulnerables a un proceso malintencionado en el momento de creación y compilación.Al utilizar un equipo que ejecuta Microsoft Windows NT 4.0 o posterior, podría ser posible que dos o más usuarios compartan el directorio TEMP.Compartir un directorio TEMP es peligroso si las dos cuentas tienen privilegios de seguridad diferentes y la cuenta del privilegio\-más alto ejecuta una aplicación mediante **XmlSerializer**.En este caso, un usuario puede incumplir la seguridad del equipo reemplazando o el archivo .cs o .dll que está compilado.Para eliminar esta preocupación, siempre asegurarse de que cada cuenta en el equipo tiene su propio perfil.De forma predeterminada, la variable de entorno TEMP señala a un directorio diferente para cada cuenta.  
  
-   Si un usuario malintencionado envía una secuencia continua de datos XML a un servidor web \(un ataque por denegación de servicio\), a continuación, **XmlSerializer** continúa procesando los datos hasta que el equipo se ejecute bajo en recursos.  
  
     Este tipo de ataque se elimina si se está utilizando un equipo que ejecuta Internet Information Services \(IIS\), y su aplicación se está ejecutando dentro de IIS.IIS representa una puerta que no procesa secuencias que sean más largas que la cantidad fija \(el valor predeterminado es 4 KB\).Si crea una aplicación que no utiliza IIS y deserializa con **XmlSerializer**, debería implementar una puerta similar que evita un ataque por denegación de servicio.  
  
-   **XmlSerializer** serializa los datos y ejecuta cualquier código utilizando cualquier tipo dado a él.  
  
     Hay dos maneras en las que un objeto malintencionado representa una amenaza.Podría ejecutar un código dañino o podría insertar un código dañino en el archivo C\# creado por **XmlSerializer**.En el primer caso, si un objeto malintencionado intenta ejecutar un procedimiento destructivo, la seguridad de acceso del código ayuda a evitar que se haga cualquier daño.En el segundo caso, hay una posibilidad teórica de que un objeto malintencionado pueda insertar de algún modo el código en el archivo C\# creado por **XmlSerializer**.Aunque se ha examinado este problema completamente, y este tipo de ataque está considerado improbable, debería tomar la precaución de nunca serializar los datos con un tipo desconocido y de poca confianza.  
  
-   Los datos confidenciales serializados podrían ser vulnerables.  
  
     Después de que el**XmlSerializer** haya serializado los datos, puede almacenarse como un archivo XML u otro almacén de datos.Si su almacén de datos está disponible para otros procesos, o está visible en una intranet o Internet, los datos se pueden robar y utilizar malévolamente.Por ejemplo, si se crea una aplicación que serializa órdenes, que incluyen la tarjeta de crédito, los datos son muy sensibles.Para ayudar a evitar esto, siempre proteja el almacén para que sus datos y los pasos de la toma lo mantenga privado.  
  
## Serialización de una clase simple  
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
  
```  
<OrderForm>  
    <OrderDate>12/12/01</OrderDate>  
</OrderForm>  
```  
  
 Para ver más ejemplos de serialización consulte [Ejemplos de serialización XML](../../../docs/framework/serialization/examples-of-xml-serialization.md).  
  
## Elementos que se pueden serializar  
 Los elementos siguientes se pueden serializar utilizando la clase **XmLSerializer**:  
  
-   Las propiedades de lectura y escritura públicas y campos de clases públicas.  
  
-   Clases que implementan **ICollection** o **IEnumerable**.  
  
    > [!NOTE]
    >  Solo se serializan las colecciones, no las propiedades públicas.  
  
-   Objetos **XmlElement**.  
  
-   Objetos **XmlNode**.  
  
-   Objetos **DataSet**.  
  
 Para obtener más información sobre la serialización o deserialización consulte [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md) y [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md).  
  
## Ventajas de utilizar serialización XML  
 La clase **XmlSerializer** proporciona un control completo y flexible al serializar un objeto como XML.Si está creando un servicio Web XML, puede aplicar atributos que controlan la serialización a las clases y miembros para asegurarse que el resultado de XML cumple con un esquema concreto.  
  
 Por ejemplo, **XmlSerializer** te permite:  
  
-   Especifique si un campo o propiedad debería estar codificada como un atributo o un elemento.  
  
-   Especifique un espacio de nombres XML para utilizar.  
  
-   Especifique el nombre de un elemento o atributo si un campo o el nombre de propiedad es impropio.  
  
 Otra ventaja de serialización XML es que no tiene ninguna restricción en las aplicaciones que desarrolla, con tal de que la secuencia XML que se genera cumpla con un esquema determinado.Imagine un esquema que se utiliza para describir los libros.Representa un título, autor, publicador y un elemento de número ISBN.Puede desarrollar una aplicación que procesa los datos XML como usted desee, por ejemplo, como una orden de libro o como un inventario de libros.En cualquier caso, el único requisito es que la secuencia XML cumple con el esquema del lenguaje de definición de esquemas XML \(XSD\) especificado.  
  
## Consideraciones de la serialización XML  
 Al utilizar la clase **XmlSerializer** debería considerarse lo siguiente:  
  
-   La herramienta Sgen.exe está diseñada expresamente para generar los ensamblados de serialización para rendimiento óptimo.  
  
-   Los datos serializados contienen solo los datos mismos y la estructura de sus clases.La identidad del tipo y la información del ensamble no están incluidas.  
  
-   Solo se pueden serializar los campos y las propiedades públicas.Las propiedades deben ser de acceso público \(métodos get y set\).Si debe serializar datos no públicos, use la clase <xref:System.Runtime.Serialization.DataContractSerializer> en lugar de la serialización XML.  
  
-   Una clase debe tener un constructor predeterminado que se va a ser serializado por **XmlSerializer**.  
  
-   Los métodos no pueden serializarse.  
  
-   **XmlSerializer** puede procesar clases que implementan de manera diferente **IEnumerable** o **ICollection** si cumplen ciertos requisitos, como sigue.  
  
     Una clase que implementa **IEnumerable** debe implementar un método **Add** público que requiere un solo parámetro.El **Add** parámetro de método debe ser coherente \(polimórfico\) con el tipo devuelto por la propiedad **IEnumerator.Current** devuelta por el método **GetEnumerator**.  
  
     Una clase que implementa **ICollection** además de **IEnumerable** \(como **CollectionBase**\) debe tener una propiedad indizada pública **Item** \(un indizador en C\#\) lo cual toma un número entero y debe tener una propiedad pública **Count** del tipo **integer**.El parámetro pasado al método **Add** debe ser del mismo tipo que aquel que devuelve la propiedad **Item** o una de las bases de dicho tipo.  
  
     Para las clases que implementan **ICollection**, los valores que se han de serializar se recuperan de la propiedad **Item** indizada, mejor que llamando a **GetEnumerator**.Asimismo, no se serializan los campos públicos y propiedades, con la excepción de campos públicos que devuelven otra clase de colección \(uno que implementa **ICollection**\).Vea un ejemplo en [Ejemplos de serialización XML](../../../docs/framework/serialization/examples-of-xml-serialization.md).  
  
## Asignación de tipo de datos XSD  
 El documento world wide web consortium \(www.w3.org\) titulado "Esquema XML parte 2: Los tipos de datos" especifica los tipos de datos simples que se permiten en un esquema del lenguaje de definición de esquemas XML \(XSD\).Para muchos de éstos \(por ejemplo, **int** y **decimal**\), hay un tipo de datos correspondiente en .NET Framework.Sin embargo, algunos tipos de datos XML no tienen un tipo de datos correspondiente en .NET Framework \(por ejemplo, el tipo de datos **NMTOKEN** \).En casos como éste, si utiliza la herramienta XML Schema Definition \([Herramienta de definición de esquema XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)\) para generar las clases a partir de un esquema, un atributo adecuado se aplica a un miembro de cadena de tipo y su propiedad **DataType** está establecida en el nombre del tipo de datos XML.Por ejemplo, si un esquema contiene un elemento denominado "MyToken" con **NMTOKEN**del tipo de datos XML, la clase generada podría contener como se muestra un miembro en el ejemplo siguiente.  
  
```vb  
<XmlElement(DataType:="NMTOKEN")> _  
Public MyToken As String  
  
```  
  
```csharp  
[XmlElement(DataType = "NMTOKEN")]  
public string MyToken;  
```  
  
 De igual forma, si está creando una clase que debe cumplir a un Esquema XML concreto \(XSD\), debería aplicar el atributo adecuado y establecer su propiedad **DataType** al nombre del tipo de datos XML deseado.  
  
 Para una lista completa de asignaciones de tipo, vea la propiedad **DataType** para cualquiera de las clases de atributos siguientes:  
  
-   <xref:System.Xml.Serialization.SoapAttributeAttribute>  
  
-   <xref:System.Xml.Serialization.SoapElementAttribute>  
  
-   <xref:System.Xml.Serialization.XmlArrayItemAttribute>  
  
-   <xref:System.Xml.Serialization.XmlAttributeAttribute>  
  
-   <xref:System.Xml.Serialization.XmlElementAttribute>  
  
-   <xref:System.Xml.Serialization.XmlRootAttribute>  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [XMLSerializer.Serialize](frlrfSystemXmlSerializationXmlSerializerClassSerializeTopic)   
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)   
 [Serialización](../../../docs/framework/serialization/index.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [FileStream](frlrfSystemIOFileStreamClassTopic)   
 [Ejemplos de serialización XML](../../../docs/framework/serialization/examples-of-xml-serialization.md)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)