---
title: Serialización (C#)
description: La serialización convierte un objeto en una secuencia de bytes para almacenarlo o transmitirlo a la memoria, a una base de datos o a un archivo.
ms.date: 01/02/2020
ms.openlocfilehash: 29625648b19c97556c107997ef9ecd3f0f971cbf
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455753"
---
# <a name="serialization-c"></a>Serialización (C#)

La serialización es el proceso de convertir un objeto en una secuencia de bytes para almacenarlo o transmitirlo a la memoria, a una base de datos o a un archivo. Su propósito principal es guardar el estado de un objeto para poder volver a crearlo cuando sea necesario. El proceso inverso se denomina deserialización.

## <a name="how-serialization-works"></a>Funcionamiento de la serialización

En esta ilustración se muestra el proceso general de la serialización:

![Gráfico serialización](./media/index/serialization-process.gif)

El objeto se serializa en una secuencia que incluye los datos. La secuencia también puede tener información sobre el tipo del objeto, como la versión, la referencia cultural y el nombre del ensamblado. A partir de esa secuencia, el objeto se puede almacenar en una base de datos, en un archivo o en memoria.

### <a name="uses-for-serialization"></a>Usos de la serialización

La serialización permite al desarrollador guardar el estado de un objeto y volver a crearlo según sea necesario, ya que proporciona almacenamiento de los objetos e intercambio de datos. A través de la serialización, un desarrollador puede realizar acciones como las siguientes:

* Enviar el objeto a una aplicación remota mediante un servicio web
* Pasar un objeto de un dominio a otro
* Pasar un objeto a través de un firewall como una cadena JSON o XML
* Mantener la seguridad o información específica del usuario entre aplicaciones

## <a name="json-serialization"></a>Serialización de JSON

El espacio de nombres <xref:System.Text.Json> contiene clases para la serialización y deserialización de notación de objetos JavaScript (JSON). JSON es un estándar abierto que se usa normalmente para compartir datos en la web.

La serialización de JSON serializa las propiedades públicas de un objeto en una cadena, una matriz de bytes o una secuencia que se ajusta a la [especificación de JSON RFC 8259](https://tools.ietf.org/html/rfc8259). Para controlar la forma en que <xref:System.Text.Json.JsonSerializer> serializa o deserializa una instancia de la clase:

* Use un objeto <xref:System.Text.Json.JsonSerializerOptions>.
* Aplique atributos del espacio de nombres <xref:System.Text.Json.Serialization> a clases o propiedades.
* [Implemente convertidores personalizados](../../../../standard/serialization/system-text-json-converters-how-to.md).

## <a name="binary-and-xml-serialization"></a>Serialización XML y binaria

El espacio de nombres <xref:System.Runtime.Serialization> contiene clases para la serialización y deserialización binaria y XML.

La serialización binaria utiliza la codificación binaria para generar una serialización compacta para usos como almacenamiento o secuencias de red basadas en socket. En la serialización binaria se serializan todos los miembros, incluso aquellos que son de solo lectura, y mejora el rendimiento.

[!INCLUDE [binary-serialization-warning](~/includes/binary-serialization-warning.md)]

La serialización XML serializa las propiedades y los campos públicos de un objeto o los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquema XML (XSD). La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos públicos se convierten a XML. <xref:System.Xml.Serialization> contiene clases para serializar y deserializar XML. Se aplican atributos a clases y a miembros de clase para controlar la forma en que <xref:System.Xml.Serialization.XmlSerializer> serializa o deserializa una instancia de la clase.

### <a name="making-an-object-serializable"></a>Conversión de un objeto en serializable

Para la serialización binaria o XML, necesita lo siguiente:

* Objeto que se va a serializar
* Secuencia para incluir el objeto serializado
* Instancia de <xref:System.Runtime.Serialization.Formatter?displayProperty=fullName>

Aplique el atributo <xref:System.SerializableAttribute> a un tipo para indicar que se pueden serializar instancias de este tipo. Si se intenta serializar pero el tipo no tiene el atributo <xref:System.SerializableAttribute>, se produce una excepción.

Para evitar que un campo se serialice, aplique el atributo <xref:System.NonSerializedAttribute>. Si un campo de un tipo serializable contiene un puntero, un controlador o alguna otra estructura de datos específica para un entorno concreto y el campo no se puede reconstituir correctamente en un entorno diferente, puede convertirlo en no serializable.

Si una clase serializada contiene referencias a objetos de otras clases marcadas como <xref:System.SerializableAttribute>, esos objetos también se serializarán.

### <a name="basic-and-custom-serialization"></a>Serialización básica y personalizada

La serialización binaria y XML se puede realizar de dos formas: de manera básica y personalizada.

La serialización básica utiliza .NET para serializar automáticamente el objeto. El único requisito es que la clase tenga el atributo <xref:System.SerializableAttribute> aplicado. <xref:System.NonSerializedAttribute> puede usarse para impedir la serialización de campos específicos.

Cuando se usa la serialización básica, el control de versiones de objetos puede causar problemas. Use la serialización personalizada si los problemas de control de versiones son importantes. La serialización básica es la manera más fácil de realizar la serialización, pero no proporciona mucho control sobre el proceso.

En la serialización personalizada, puede especificar exactamente qué objetos se serializarán y cómo se llevará a cabo la serialización. La clase debe marcarse como <xref:System.SerializableAttribute> e implementar la interfaz <xref:System.Runtime.Serialization.ISerializable>. Si quiere que el objeto también se deserialice de forma personalizada, use un constructor personalizado.

## <a name="designer-serialization"></a>Serialización de diseñador

La serialización de diseñador es una forma especial de serialización que conlleva el tipo de persistencia de objeto asociado a las herramientas de desarrollo. La serialización de diseñador es un proceso que consiste en convertir un gráfico de objetos en un archivo de código fuente que puede utilizarse posteriormente para recuperar el gráfico de objetos. Un archivo de código fuente puede contener código, marcado o incluso información de la tabla SQL.

## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> Temas relacionados y ejemplos  

En [Información general de System.Text.Json](../../../../standard/serialization/system-text-json-overview.md) se muestra cómo obtener la biblioteca `System.Text.Json`.

En [Procedimiento para serializar y deserializar JSON en .NET](../../../../standard/serialization/system-text-json-how-to.md)
se muestra cómo leer y escribir datos de objetos a y desde JSON mediante la clase <xref:System.Text.Json.JsonSerializer>.

[Tutorial: Conservar un objeto en Visual Studio (C#)](walkthrough-persisting-an-object-in-visual-studio.md)  
Se explica cómo se puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.

[Procedimiento para leer datos de objeto de un archivo XML (C#)](how-to-read-object-data-from-an-xml-file.md)  
Se muestra cómo leer los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.

[Procedimiento para escribir datos de objeto en un archivo XML (C#)](how-to-write-object-data-to-an-xml-file.md)  
Se muestra cómo escribir el objeto de una clase en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.
