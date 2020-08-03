---
title: LINQ to XML frente a DOM (C#)
description: Obtenga información sobre algunas diferencias clave entre LINQ to XML y la API de programación XML de Document Object Model (DOM) de W3C.
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: f5fc3fd7869079d47d7c9031e3668afeed7a117b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165340"
---
# <a name="linq-to-xml-vs-dom-c"></a>LINQ to XML frente a DOM (C#)
En esta sección se describen algunas diferencias fundamentales entre [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] y la API de programación XML predominante actual, Document Object Model (DOM) W3C.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Nuevas formas de crear árboles XML  
 En DOM W3C, los árboles XML se crean de abajo arriba; es decir, se crea un documento, se crean elementos y, a continuación, se agregan los elementos al documento.  
  
 Por ejemplo, a continuación se muestra una forma típica de crear un árbol XML usando la implementación de DOM de Microsoft, <xref:System.Xml.XmlDocument>:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
XmlElement phone1 = doc.CreateElement("Phone");  
phone1.SetAttribute("Type", "Home");  
phone1.InnerText = "206-555-0144";
XmlElement phone2 = doc.CreateElement("Phone");  
phone2.SetAttribute("Type", "Work");  
phone2.InnerText = "425-555-0145";
XmlElement street1 = doc.CreateElement("Street1");
street1.InnerText = "123 Main St";  
XmlElement city = doc.CreateElement("City");  
city.InnerText = "Mercer Island";  
XmlElement state = doc.CreateElement("State");  
state.InnerText = "WA";  
XmlElement postal = doc.CreateElement("Postal");  
postal.InnerText = "68042";  
XmlElement address = doc.CreateElement("Address");  
address.AppendChild(street1);  
address.AppendChild(city);  
address.AppendChild(state);  
address.AppendChild(postal);  
XmlElement contact = doc.CreateElement("Contact");  
contact.AppendChild(name);  
contact.AppendChild(phone1);  
contact.AppendChild(phone2);  
contact.AppendChild(address);  
XmlElement contacts = doc.CreateElement("Contacts");  
contacts.AppendChild(contact);  
doc.AppendChild(contacts);  
```  
  
 Este estilo de codificación no proporciona mucha información visual acerca de la estructura del árbol XML. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] admite este enfoque para crear un árbol XML, pero también admite un enfoque alternativo, la *construcción funcional*. La construcción funcional usa los constructores <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute> para crear un árbol XML.  
  
 A continuación se muestra cómo se crea el mismo árbol XML mediante la construcción funcional [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144",
                new XAttribute("Type", "Home")),  
            new XElement("phone", "425-555-0145",  
                new XAttribute("Type", "Work")),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Tenga en cuenta que si se aplica la sangría al código para crear el árbol XML, se mostrará la estructura XML subyacente.  
  
 Para obtener más información, vea [Creating XML Trees (C#)](./linq-to-xml-overview.md) (Crear árboles XML (C#))  
  
## <a name="working-directly-with-xml-elements"></a>Trabajar directamente con elementos XML  
 La programación con XML suele centrarse en elementos XML y quizás en los atributos. En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede trabajar directamente con atributos y elementos XML. Por ejemplo, puede realizar lo siguiente:  
  
- Crear elementos XML sin usar un objeto de documento. Esto simplifica la programación cuando se tiene que trabajar con fragmentos de árboles XML.  
  
- Cargar objetos `T:System.Xml.Linq.XElement` directamente de un archivo XML.  
  
- Serializar objetos `T:System.Xml.Linq.XElement` a un archivo o una secuencia.  
  
 Compare esto con modelo DOM del consorcio W3C, en el que el documento XML se usa como contenedor lógico para el árbol XML. En DOM, los nodos XML, incluyendo elementos y atributos, se deben crear en el contexto de un documento XML. A continuación se muestra un fragmento del código para crear un nombre de elemento en DOM:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 Si desea usar un elemento en varios documentos, debe importar los nodos en los documentos. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] evita este grado de complejidad.  
  
 Cuando se utiliza LINQ to XML, se usa la clase <xref:System.Xml.Linq.XDocument> solamente si se desea agregar un comentario o una instrucción de procesamiento en el nivel de raíz del documento.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Control simplificado de nombres y espacios de nombres  
 Controlar nombres, espacios de nombres y prefijos de espacios de nombres suele ser una parte compleja de la programación XML. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica los nombres y los espacios de nombres al eliminar el requisito de tener que tratar con prefijos de espacios de nombres. Si lo desea, puede controlar los prefijos de espacios de nombres. Pero si decide no controlar explícitamente los prefijos de espacios de nombres, durante la serialización [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] asignará prefijos de espacios de nombres si son necesarios, o serializará con espacios de nombres predeterminados si no lo son. Si se usan espacios de nombres predeterminados, no habrá prefijos de espacios de nombres en el documento resultante. Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 Otro problema de DOM consiste en que no permite cambiar el nombre de un nodo. Por el contrario, hay que crear un nuevo nodo y copiar en él todos los nodos secundarios, por lo que se pierde la identidad del nodo original. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] evita este problema al permitir que se establezca la propiedad <xref:System.Xml.Linq.XName> en un nodo.  
  
## <a name="static-method-support-for-loading-xml"></a>Compatibilidad con el método estático para cargar XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permite cargar XML mediante métodos estáticos en lugar de métodos de instancia. Esto simplifica la carga y el análisis. Para más información, consulte [Procedimiento para cargar un documento XML desde un archivo (C#)](./how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Eliminación de la compatibilidad con construcciones DTD  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica aún más la programación XML quitando la compatibilidad con entidades y referencias a entidades. La administración de entidades es compleja y su uso es muy poco común. La eliminación de la compatibilidad aumenta el rendimiento y simplifica la interfaz de programación. Cuando se rellena un árbol de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se expanden todas las entidades DTD.  
  
## <a name="support-for-fragments"></a>Compatibilidad con fragmentos  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] no proporciona un equivalente para la clase `XmlDocumentFragment`. En cambio, es bastante común que el concepto `XmlDocumentFragment` se pueda controlar mediante el resultado de una consulta que se escribe como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XNode> o <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>.  
  
## <a name="support-for-xpathnavigator"></a>Compatibilidad con XPathNavigator  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona compatibilidad con <xref:System.Xml.XPath.XPathNavigator> mediante los métodos de extensión del espacio de nombres <xref:System.Xml.XPath?displayProperty=nameWithType>. Para obtener más información, vea <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
## <a name="support-for-white-space-and-indentation"></a>Compatibilidad con espacios en blanco y sangría  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] trata los espacios en blanco de forma más sencilla que DOM.  
  
 Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría. Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos. Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada. Es posible que no desee modificar esta sangría de ninguna forma. En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede conseguirlo si preserva los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] almacena un espacio en blanco como un nodo <xref:System.Xml.Linq.XText>, en lugar de tener un tipo de nodo <xref:System.Xml.XmlNodeType.Whitespace> especializado, al igual que DOM.  
  
## <a name="support-for-annotations"></a>Compatibilidad con anotaciones  
 Los elementos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] admiten un conjunto extensible de anotaciones. Esto puede resultar útil para realizar un seguimiento de información diversa de un elemento, como la información de esquema, información acerca de si un elemento está enlazado a una interfaz de usuario o cualquier otro tipo de información específica de una aplicación. Para obtener más información, vea [Anotaciones en LINQ to XML](./linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Compatibilidad con la información de esquema  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona compatibilidad con la validación XSD mediante métodos de extensión en el espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType>. Puede validar que un árbol XML sea compatible con un XSD. Puede rellenar el árbol XML con el conjunto de información posterior a la validación del esquema (PSVI). Para más información, consulte [Procedimiento para validar con XSD (LINQ to XML) (C#)](./how-to-validate-using-xsd-linq-to-xml.md) y <xref:System.Xml.Schema.Extensions>.
  
## <a name="see-also"></a>Consulte también

- [Introducción (LINQ to XML)](./linq-to-xml-overview.md)
