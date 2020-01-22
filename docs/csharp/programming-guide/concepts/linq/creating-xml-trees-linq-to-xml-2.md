---
title: Crear árboles XML en C# (LINQ to XML)
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: a77171ebbc07e54f6988fb97aff197b4c6d31721
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594628"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a>Crear árboles XML en C# (LINQ to XML)
En esta sección encontrará información acerca de cómo crear árboles XML en C#.  
  
 Para obtener información sobre cómo usar los resultados de las consultas LINQ como contenido de un <xref:System.Xml.Linq.XElement>, vea [Construcción funcional (LINQ to XML) (C#)](./functional-construction-linq-to-xml.md).  
  
## <a name="constructing-elements"></a>Elementos de construcción
 Las firmas de los constructores <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute> le permiten pasar los contenidos del elemento o atributo como argumentos del constructor. Dado que uno de los constructores recibe un número variable de argumentos, podrá pasar tantos elementos secundarios como desee. Por supuesto, cada uno de esos elementos secundarios podrá contener sus propios elementos secundarios. Para cualquier elemento, podrá agregar cuantos atributos desee.  
  
 Cuando se agregan objetos <xref:System.Xml.Linq.XNode> (incluyendo el objeto <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute>, si el contenido nuevo no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML. Si el contenido nuevo ya tiene un elemento primario y forma parte de otro árbol XML, el nuevo contenido se clonará y ese clon se asociará al árbol XML. El último ejemplo de este tema muestra este comportamiento.  
  
 Para crear un `contacts`<xref:System.Xml.Linq.XElement>, podría utilizar el siguiente código:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Si se aplica correctamente la sangría, el código que construye los objetos <xref:System.Xml.Linq.XElement> se asemeja mucho a la estructura del contenido XML subyacente.  
  
## <a name="xelement-constructors"></a>Constructores de XElement  
 La clase <xref:System.Xml.Linq.XElement> utiliza los siguientes constructores para llevar a cabo una construcción funcional. Observe que existen algunos constructores más para <xref:System.Xml.Linq.XElement>, pero, dado que no se utilizan para el proceso de construcción funcional, no se detallarán aquí.  
  
|Constructor|DESCRIPCIÓN|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|Crea una interfaz <xref:System.Xml.Linq.XElement>. El parámetro `name` especifica el nombre del elemento; `content` especifica el contenido del elemento.|  
|`XElement(XName name)`|Crea un <xref:System.Xml.Linq.XElement> cuyo <xref:System.Xml.Linq.XName> se inicializa con el nombre especificado.|  
|`XElement(XName name, params object[] content)`|Crea un <xref:System.Xml.Linq.XElement> cuyo <xref:System.Xml.Linq.XName> se inicializa con el nombre especificado. Los atributos y/o elementos secundarios se crean a partir de los contenidos de la lista de parámetros.|  
  
 El parámetro `content` es extremadamente flexible. Admite cualquier tipo de objeto que sea un elemento secundario válido de un <xref:System.Xml.Linq.XElement>. Se aplicarán las siguientes reglas a los diferentes tipos de objetos pasados en este parámetros:  
  
- Una cadena se agrega como contenido de tipo texto.  
  
- Un <xref:System.Xml.Linq.XElement> se agrega como un elemento secundario.  
  
- Un <xref:System.Xml.Linq.XAttribute> se agrega como un atributo.  
  
- Un <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment> o un <xref:System.Xml.Linq.XText> se agregan como un contenido secundario.  
  
- Un <xref:System.Collections.IEnumerable> es un tipo enumerado y se aplicarán estas reglas recursivamente a los resultados.  
  
- Para el resto de tipos, se llamará a su método `ToString` y se agregará el resultado como contenido de tipo texto.  
  
### <a name="creating-an-xelement-with-content"></a>Creación de un XElement con contenidos  
 Puede crear un <xref:System.Xml.Linq.XElement> que contenga un contenido simple con una única llamada a método. Para ello, especifique el contenido como segundo parámetro, tal y como sigue:  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 Puede pasar cualquier tipo de objeto como contenido. Por ejemplo, el siguiente código crea un elemento que contiene un número de punto flotante como contenido:  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 Al número de punto flotante se le aplica la conversión boxing y se pasa al constructor. El número se convierte entonces en una cadena y se utiliza como contenido del elemento.  
  
### <a name="creating-an-xelement-with-a-child-element"></a>Creación de un XElement con un elemento secundario  
 Si pasa una instancia de la clase <xref:System.Xml.Linq.XElement> para el argumento del contenido, el constructor creará un elemento que tiene un elemento secundario:  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a>Creación de un XElement con varios elementos secundarios  
 Para el contenido, puede pasar tantos objetos <xref:System.Xml.Linq.XElement> como desee. Cada uno de los objetos <xref:System.Xml.Linq.XElement> se incluye como elemento secundario.  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 Si se extiende el ejemplo anterior, es posible crear un árbol XML completo, tal y como sigue:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),                                                   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  

### <a name="creating-an-xelement-with-an-xattribute"></a>Creación de un XElement con un XAttribute
 Si pasa una instancia de la clase <xref:System.Xml.Linq.XAttribute> para el argumento del contenido, el constructor creará un elemento con un atributo:

```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>
```   

### <a name="creating-an-empty-element"></a>Creación de un elemento vacío  
 Para crear un <xref:System.Xml.Linq.XElement> vacío, no pase ningún contenido al constructor. El siguiente ejemplo crea un elemento vacío:  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a>Diferencias entre asociar y clonar  
 Como mencionamos anteriormente, cuando se agregan objetos <xref:System.Xml.Linq.XNode> (incluyendo el objeto <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute>, si el contenido nuevo no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML. Si el contenido nuevo ya tiene un elemento primario y forma parte de otro árbol XML, el nuevo contenido se clonará y ese clon se asociará al árbol XML.  

En el siguiente ejemplo se demuestra qué ocurre si agrega un elemento que tiene elemento primario a un árbol y qué ocurre si agrega un elemento que no tenga elemento primario a un árbol.

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a>Vea también

- [Creación de árboles XML (C#)](./linq-to-xml-overview.md)
