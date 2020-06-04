---
title: Serialización
ms.date: 07/20/2015
ms.assetid: 67379a76-5465-4af8-a781-0b0b25a62d9a
ms.openlocfilehash: db14147a23940fa2403613036750be1bca566e8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413146"
---
# <a name="serialization-visual-basic"></a>Serialización (Visual Basic)
La serialización es un proceso que consiste en convertir un objeto en una secuencia de bytes para almacenar el objeto o transmitirlo a la memoria, a una base de datos o a un archivo. Su propósito principal es guardar el estado de un objeto para poder volver a crearlo cuando sea necesario. El proceso inverso se denomina deserialización.  
  
## <a name="how-serialization-works"></a>Funcionamiento de la serialización  
 En esta ilustración se muestra el proceso general de la serialización.  
  
![Gráfico serialización](./media/index/serialization-process.gif)
  
 El objeto se serializa en una secuencia, que incluye no solo los datos, sino también la información sobre el tipo de objeto, como su versión, referencia cultural y nombre de ensamblado. A partir de esa secuencia, el almacenamiento se puede realizar en una base de datos, en un archivo o en la memoria.  
  
### <a name="uses-for-serialization"></a>Usos de la serialización  
 La serialización permite al desarrollador guardar el estado de un objeto y volver a crearlo según sea necesario, gracias a que proporciona almacenamiento de los objetos e intercambio de datos. A través de la serialización, un desarrollador puede realizar acciones como enviar un objeto a una aplicación remota por medio de un servicio web, pasar un objeto de un dominio a otro, pasar un objeto a través de un firewall como una cadena XML o mantener la seguridad o información específica del usuario entre aplicaciones.  
  
### <a name="making-an-object-serializable"></a>Conversión de un objeto en serializable  
 Para serializar un objeto, necesita el objeto que se va a serializar, una secuencia que contenga el objeto serializado y un <xref:System.Runtime.Serialization.Formatter>. <xref:System.Runtime.Serialization> contiene las clases necesarias para serializar y deserializar objetos.  
  
 Aplique el atributo <xref:System.SerializableAttribute> a un tipo para indicar que se pueden serializar instancias de este tipo. Si se intenta serializar pero el tipo no tiene el atributo <xref:System.SerializableAttribute>, se produce una excepción <xref:System.Runtime.Serialization.SerializationException>.  
  
 Si no quiere que un campo dentro de la clase sea serializable, aplique el atributo <xref:System.NonSerializedAttribute>. Si un campo de un tipo serializable contiene un puntero, un controlador o alguna otra estructura de datos específica para un entorno concreto y el campo no se puede reconstituir correctamente en un entorno diferente, puede convertirlo en no serializable.  
  
 Si una clase serializada contiene referencias a objetos de otras clases marcadas como <xref:System.SerializableAttribute>, esos objetos también se serializarán.  
  
## <a name="binary-and-xml-serialization"></a>Serialización XML y binaria  
 Se puede usar la serialización binaria y XML. En la serialización binaria, se serializan todos los miembros, incluso aquellos que son de solo lectura, y se mejora el rendimiento. La serialización XML proporciona código más legible, así como mayor flexibilidad para compartir objetos y utilizarlos para fines de interoperabilidad.  
  
### <a name="binary-serialization"></a>Serialización binaria  
 La serialización binaria utiliza la codificación binaria para generar una serialización compacta para usos como almacenamiento o secuencias de red basadas en socket.  
  
### <a name="xml-serialization"></a>Serialización XML  
 La serialización XML serializa las propiedades y los campos públicos de un objeto o los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquema XML (XSD). La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos públicos se convierten a XML. <xref:System.Xml.Serialization> contiene las clases necesarias para serializar y deserializar XML.  
  
 Se pueden aplicar atributos a clases y a miembros de clase para controlar la forma en que <xref:System.Xml.Serialization.XmlSerializer> serializa o deserializa una instancia de la clase.  
  
## <a name="basic-and-custom-serialization"></a>Serialización básica y personalizada  
 La serialización puede realizarse de dos formas, es decir, de manera básica y también personalizada. La serialización básica utiliza .NET Framework para serializar automáticamente el objeto.  
  
### <a name="basic-serialization"></a>Serialización básica  
 El único requisito de la serialización básica es que el objeto tenga aplicado el atributo <xref:System.SerializableAttribute>. <xref:System.NonSerializedAttribute> puede usarse para impedir la serialización de campos específicos.  
  
 Cuando se utiliza la serialización básica, el control de versiones de objetos puede crear problemas, en cuyo caso la serialización personalizada puede ser preferible. La serialización básica es la manera más fácil de realizar la serialización, pero no proporciona mucho control sobre el proceso.  
  
### <a name="custom-serialization"></a>Serialización personalizada  
 En la serialización personalizada, puede especificar exactamente qué objetos se serializarán y cómo se llevará a cabo la serialización. La clase debe marcarse como <xref:System.SerializableAttribute> e implementar la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
 Si desea que el objeto se deserialice también de forma personalizada, debe usar un constructor personalizado.  
  
## <a name="designer-serialization"></a>Serialización de diseñador  
 La serialización de diseñador es una forma especial de serialización que abarca el tipo de persistencia de objeto normalmente asociado a las herramientas de desarrollo. La serialización de diseñador es un proceso que consiste en convertir un gráfico de objetos en un archivo de código fuente que puede utilizarse posteriormente para recuperar el gráfico de objetos. Un archivo de código fuente puede contener código, marcado o incluso información de la tabla SQL.  
  
## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> Temas relacionados y ejemplos  
 [Tutorial: Conservar un objeto en Visual Studio (Visual Basic)](walkthrough-persisting-an-object-in-visual-studio.md)  
 Se explica cómo se puede usar la serialización para conservar los datos de un objeto entre instancias, lo que le permite almacenar valores y recuperarlos la próxima vez que se cree una instancia del objeto.  
  
 [How to: Read Object Data from an XML File (Visual Basic)](how-to-read-object-data-from-an-xml-file.md) (Lectura de datos de objetos de un archivo XML [Visual Basic])  
 Se muestra cómo leer los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.  
  
 [How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md) (Escritura de datos de objetos en un archivo XML [Visual Basic])  
 Se muestra cómo escribir el objeto de una clase en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.
