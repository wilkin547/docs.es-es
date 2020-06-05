---
title: LINQ to XML frente a DOM
ms.date: 07/20/2015
ms.assetid: 18c36130-d598-40b7-9007-828232252978
ms.openlocfilehash: 5813ca410e3e2b1ec284681451d0c0cec6f5e393
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389350"
---
# <a name="linq-to-xml-vs-dom-visual-basic"></a>LINQ to XML frente a DOM (Visual Basic) (LINQ to XML frente a DOM)
En esta sección se describen algunas diferencias fundamentales entre [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] y la API de programación XML predominante actual, Document Object Model (DOM) W3C.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Nuevas formas de crear árboles XML  
 En DOM W3C, los árboles XML se crean de abajo arriba; es decir, se crea un documento, se crean elementos y, a continuación, se agregan los elementos al documento.  
  
 Por ejemplo, a continuación se muestra una forma típica de crear un árbol XML usando la implementación de DOM de Microsoft, <xref:System.Xml.XmlDocument>:  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
Dim phone1 As XmlElement = doc.CreateElement("Phone")  
phone1.SetAttribute("Type", "Home")  
phone1.InnerText = "206-555-0144"  
Dim phone2 As XmlElement = doc.CreateElement("Phone")  
phone2.SetAttribute("Type", "Work")  
phone2.InnerText = "425-555-0145"  
Dim street1 As XmlElement = doc.CreateElement("Street1")  
street1.InnerText = "123 Main St"  
Dim city As XmlElement = doc.CreateElement("City")  
city.InnerText = "Mercer Island"  
Dim state As XmlElement = doc.CreateElement("State")  
state.InnerText = "WA"  
Dim postal As XmlElement = doc.CreateElement("Postal")  
postal.InnerText = "68042"  
Dim address As XmlElement = doc.CreateElement("Address")  
address.AppendChild(street1)  
address.AppendChild(city)  
address.AppendChild(state)  
address.AppendChild(postal)  
Dim contact As XmlElement = doc.CreateElement("Contact")  
contact.AppendChild(name)  
contact.AppendChild(phone1)  
contact.AppendChild(phone2)  
contact.AppendChild(address)  
Dim contacts As XmlElement = doc.CreateElement("Contacts")  
contacts.AppendChild(contact)  
doc.AppendChild(contacts)  
Console.WriteLine(doc.OuterXml)  
```  
  
 Este estilo de codificación no proporciona mucha información visual acerca de la estructura del árbol XML. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] admite este enfoque para crear un árbol XML, pero también admite un enfoque alternativo, la *construcción funcional*. En Visual Basic, la construcción funcional utiliza literales XML para generar un árbol XML.  
  
 A continuación se muestra cómo se crea el mismo árbol XML mediante la construcción funcional [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]:  
  
```vb  
Dim contacts = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="Home">206-555-0144</Phone>  
            <Phone Type="Work">425-555-0145</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Tenga en cuenta que si se aplica la sangría al código para crear el árbol XML, se mostrará la estructura XML subyacente.  
  
 Para obtener más información, vea [crear árboles XML (Visual Basic)](creating-xml-trees.md).  
  
## <a name="working-directly-with-xml-elements"></a>Trabajar directamente con elementos XML  
 La programación con XML suele centrarse en elementos XML y quizás en los atributos. En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede trabajar directamente con atributos y elementos XML. Por ejemplo, puede realizar lo siguiente:  
  
- Crear elementos XML sin usar un objeto de documento. Esto simplifica la programación cuando se tiene que trabajar con fragmentos de árboles XML.  
  
- Cargar objetos `T:System.Xml.Linq.XElement` directamente de un archivo XML.  
  
- Serializar objetos `T:System.Xml.Linq.XElement` a un archivo o una secuencia.  
  
 Compare esto con modelo DOM del consorcio W3C, en el que el documento XML se usa como contenedor lógico para el árbol XML. En DOM, los nodos XML, incluyendo elementos y atributos, se deben crear en el contexto de un documento XML. A continuación se muestra un fragmento del código para crear un nombre de elemento en DOM:  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 Si desea usar un elemento en varios documentos, debe importar los nodos en los documentos. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] evita este grado de complejidad.  
  
 Cuando se utiliza LINQ to XML, se usa la clase <xref:System.Xml.Linq.XDocument> solamente si se desea agregar un comentario o una instrucción de procesamiento en el nivel de raíz del documento.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Control simplificado de nombres y espacios de nombres  
 Controlar nombres, espacios de nombres y prefijos de espacios de nombres suele ser una parte compleja de la programación XML. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica los nombres y los espacios de nombres al eliminar el requisito de tener que tratar con prefijos de espacios de nombres. Si lo desea, puede controlar los prefijos de espacios de nombres. Pero si decide no controlar explícitamente los prefijos de espacios de nombres, durante la serialización [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] asignará prefijos de espacios de nombres si son necesarios, o serializará con espacios de nombres predeterminados si no lo son. Si se usan espacios de nombres predeterminados, no habrá prefijos de espacios de nombres en el documento resultante. Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 Otro problema de DOM consiste en que no permite cambiar el nombre de un nodo. Por el contrario, hay que crear un nuevo nodo y copiar en él todos los nodos secundarios, por lo que se pierde la identidad del nodo original. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] evita este problema al permitir que se establezca la propiedad <xref:System.Xml.Linq.XName> en un nodo.  
  
## <a name="static-method-support-for-loading-xml"></a>Compatibilidad con el método estático para cargar XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permite cargar XML mediante métodos estáticos en lugar de métodos de instancia. Esto simplifica la carga y el análisis. Para obtener más información, vea [Cómo: cargar XML desde un archivo (Visual Basic)](how-to-load-xml-from-a-file.md).  
  
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
 Los elementos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] admiten un conjunto extensible de anotaciones. Esto puede resultar útil para realizar un seguimiento de información diversa de un elemento, como la información de esquema, información acerca de si un elemento está enlazado a una interfaz de usuario o cualquier otro tipo de información específica de una aplicación. Para obtener más información, vea [Anotaciones en LINQ to XML](linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Compatibilidad con la información de esquema  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona compatibilidad con la validación XSD mediante métodos de extensión en el espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType>. Puede validar que un árbol XML sea compatible con un XSD. Puede rellenar el árbol XML con el conjunto de información posterior a la validación del esquema (PSVI). Para obtener más información, vea [Cómo: validar con XSD](how-to-validate-using-xsd-linq-to-xml.md) y <xref:System.Xml.Schema.Extensions> .  
  
## <a name="see-also"></a>Vea también

- [Introducción (LINQ to XML)](getting-started-linq-to-xml.md)
