---
title: Controlar la serialización XML mediante atributos
description: Los atributos se pueden utilizar para controlar la serialización XML de un objeto o crear una secuencia XML alternativa a partir del mismo conjunto de clases.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, serializing
- XML serialization, examples
- derived classes, serializing
- arrays, serializing
- XML serialization, attributes
- preventing serialization
- attributes [.NET Framework], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: 4fc7667a2123a106b995a1ea3a31da4551ca650e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375962"
---
# <a name="controlling-xml-serialization-using-attributes"></a>Controlar la serialización XML mediante atributos

Los atributos se pueden utilizar para controlar la serialización XML de un objeto o crear una secuencia XML alternativa a partir del mismo conjunto de clases. Para obtener más información sobre la creación de una secuencia XML alternativa vea [Procedimiento para especificar un nombre de elemento alternativo para una secuencia XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).

> [!NOTE]
> Si el código XML generado se ajusta a la sección 5 del documento [Protocolo simple de acceso a objetos (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), del Consorcio WWC (W3C), use los atributos enumerados en [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md).

La clase o nombre de miembro determina, de forma predeterminada, un nombre del elemento XML. En una clase simple denominada `Book`, un campo denominado `ISBN` generará una etiqueta del elemento XML \<ISBN> como se muestra en el ejemplo siguiente.

```vb
Public Class Book
    Public ISBN As String
End Class
' When an instance of the Book class is serialized, it might
' produce this XML:
' <ISBN>1234567890</ISBN>.
```

```csharp
public class Book
{
    public string ISBN;
}
// When an instance of the Book class is serialized, it might
// produce this XML:
// <ISBN>1234567890</ISBN>.
```

Se puede cambiar este comportamiento predeterminado si desea dar un nuevo nombre al elemento. El código siguiente muestra cómo un atributo habilita esto estableciendo la propiedad <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> de <xref:System.Xml.Serialization.XmlElementAttribute>.

```vb
Public Class TaxRates
   < XmlElement(ElementName = "TaxRate")> _
    Public ReturnTaxRate As Decimal
End Class
```

```csharp
public class TaxRates {
    [XmlElement(ElementName = "TaxRate")]
    public decimal ReturnTaxRate;
}
```

Para obtener más información sobre atributos, vea [Atributos](../../../docs/standard/attributes/index.md). Para obtener una lista de atributos que controlan la serialización XML, vea [Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md).

## <a name="controlling-array-serialization"></a>Controlar la serialización de la matriz

Los atributos <xref:System.Xml.Serialization.XmlArrayAttribute> y <xref:System.Xml.Serialization.XmlArrayItemAttribute> están diseñados para controlar la serialización de las matrices. Con estos atributos, puede controlar el nombre de elemento, el espacio de nombres y el tipo de datos del esquema XML (XSD) (como se define en el documento de World Wide Web Consortium [www.w3.org] titulado "Esquema XML parte 2: tipos de datos"). También puede especificar los tipos que pueden estar incluidos en una matriz.

<xref:System.Xml.Serialization.XmlArrayAttribute> determinará las propiedades del elemento envolvente XML que resulta cuando se serializa una matriz. Por ejemplo, de forma predeterminada, serializar la matriz siguiente producirá un elemento XML denominado `Employees`. El elemento `Employees` contendrá una serie de elementos denominados según el tipo de matriz `Employee`.

```vb
Public Class Group
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
```

```csharp
public class Group {
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
```

Una instancia serializada se podría parecer a lo siguiente.

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

Aplicando <xref:System.Xml.Serialization.XmlArrayAttribute>, puede cambiar el nombre del elemento XML, como sigue.

```vb
Public Class Group
    <XmlArray("TeamMembers")> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlArray("TeamMembers")]
    public Employee[] Employees;
}
```

El XML resultante puede parecerse a lo siguiente.

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<xref:System.Xml.Serialization.XmlArrayItemAttribute>, por otro lado, controla cómo se serializan los elementos contenidos en la matriz. Observe que el atributo se aplica al campo que devuelve la matriz.

```vb
Public Class Group
    <XmlArrayItem("MemberName")> _
    Public Employee() As Employees
End Class
```

```csharp
public class Group {
    [XmlArrayItem("MemberName")]
    public Employee[] Employees;
}
```

El XML resultante puede parecerse a lo siguiente.

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a>Serializar las clases derivadas

Otro uso de <xref:System.Xml.Serialization.XmlArrayItemAttribute> es permitir la serialización de clases derivadas. Por ejemplo, otra clase denominada `Manager` que deriva de `Employee` se puede agregar al ejemplo anterior. Si no aplica <xref:System.Xml.Serialization.XmlArrayItemAttribute>, se producirá un error en el código en tiempo de ejecución porque no se reconocerá el tipo de clase derivada. Para solucionar esto, aplique dos veces el atributo, estableciendo la propiedad <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> cada vez, para cada tipo aceptable (base y derivado).

```vb
Public Class Group
    <XmlArrayItem(Type:=GetType(Employee)), _
    XmlArrayItem(Type:=GetType(Manager))> _
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
Public Class Manager
Inherits Employee
    Public Level As Integer
End Class
```

```csharp
public class Group {
    [XmlArrayItem(Type = typeof(Employee)),
    XmlArrayItem(Type = typeof(Manager))]
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
public class Manager:Employee {
    public int Level;
}
```

Una instancia serializada se podría parecer a lo siguiente.

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
    <Employee xsi:type = "Manager">
        <Name>Ann</Name>
        <Level>3</Level>
    </Employee>
</Employees>
</Group>
```

## <a name="serializing-an-array-as-a-sequence-of-elements"></a>Serializar una matriz como una secuencia de elementos

También puede serializar una matriz como una secuencia plana de elementos XML aplicando <xref:System.Xml.Serialization.XmlElementAttribute> al campo que devuelve la matriz como sigue.

```vb
Public Class Group
    <XmlElement> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlElement]
    public Employee[] Employees;
}
```

Una instancia serializada se podría parecer a lo siguiente.

```xml
<Group>
<Employees>
    <Name>Haley</Name>
</Employees>
<Employees>
    <Name>Noriko</Name>
</Employees>
<Employees>
    <Name>Marco</Name>
</Employees>
</Group>
```

Otra manera de diferenciar las dos secuencias XML es utilizar la herramienta de definición de esquemas XML para generar los archivos de documento de esquema XML (XSD) a partir del código compilado. (Para obtener más información sobre el uso de la herramienta, vea [La herramienta de definición de esquema XML y serialización XML](the-xml-schema-definition-tool-and-xml-serialization.md)). Cuando no se aplica ningún atributo al campo, el esquema describe el elemento de la manera siguiente.

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

Cuando <xref:System.Xml.Serialization.XmlElementAttribute> se aplica al campo, el esquema resultante describe el elemento como sigue.

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a>Serializar un ArrayList

La clase <xref:System.Collections.ArrayList> puede contener una colección de objetos diversos. Además puede utilizar <xref:System.Collections.ArrayList> tantas veces como utiliza la matriz. En lugar de crear un campo que devuelve una matriz de objetos escritos, sin embargo, puede crear un campo que devuelve un <xref:System.Collections.ArrayList>único. Sin embargo, al igual que con las matrices, debe informar a<xref:System.Xml.Serialization.XmlSerializer> de los tipos de objetos <xref:System.Collections.ArrayList> que contiene. Para lograr esto, asigne varias instancias de <xref:System.Xml.Serialization.XmlElementAttribute> al campo, como se muestra en el ejemplo siguiente.

```vb
Public Class Group
    <XmlElement(Type:=GetType(Employee)), _
    XmlElement(Type:=GetType(Manager))> _
    Public Info As ArrayList
End Class
```

```csharp
public class Group {
    [XmlElement(Type = typeof(Employee)),
    XmlElement(Type = typeof(Manager))]
    public ArrayList Info;
}
```

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a>Controle la serialización de clases utilizando XmlRootAttribute y XmlTypeAttribute

Existen dos atributos que pueden aplicarse a la clase (y solamente una clase): <xref:System.Xml.Serialization.XmlRootAttribute> y <xref:System.Xml.Serialization.XmlTypeAttribute>. Estos atributos son muy similares. <xref:System.Xml.Serialization.XmlRootAttribute> se puede aplicar a solo una clase: la clase que, cuando se serializa, representa el elemento de apertura y cierre del documento XML, en otras palabras, el elemento raíz. <xref:System.Xml.Serialization.XmlTypeAttribute>, por otro lado, se puede aplicar a cualquier clase, incluso a la clase raíz.

Por ejemplo, en los ejemplos anteriores, la clase `Group` es la clase raíz y todos sus campos públicos y propiedades se vuelven elementos XML situados en el documento XML. Además, solo puede haber una clase de raíz. Aplicando <xref:System.Xml.Serialization.XmlRootAttribute>, puede controlar la secuencia XML generada por <xref:System.Xml.Serialization.XmlSerializer>. Por ejemplo, puede cambiar el nombre de elemento y espacio de nombres.

<xref:System.Xml.Serialization.XmlTypeAttribute> le permite controlar el esquema del XML generado. Esta función es útil si se necesita publicar el esquema a través de un servicio Web XML. En el siguiente ejemplo, se aplica <xref:System.Xml.Serialization.XmlTypeAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la misma clase.

```vb
<XmlRoot("NewGroupName"), _
XmlType("NewTypeName")> _
Public Class Group
    Public Employees() As Employee
End Class
```

```csharp
[XmlRoot("NewGroupName")]
[XmlType("NewTypeName")]
public class Group {
    public Employee[] Employees;
}
```

Si esta clase está compilada, y la herramienta de definición de esquemas XML se utiliza para generar su esquema, encontraría el XML siguiente que describe `Group`.

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

En contraste, si fuera serializar una instancia de la clase, solo `NewGroupName` se buscarían en el documento XML.

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a>Evitar la serialización con XmlIgnoreAttribute

Podrían darse situaciones en las que una propiedad pública o el campo no necesite ser serializado. Por ejemplo, un campo o propiedad se puede utilizar para contener los metadatos. En casos como éste, aplique <xref:System.Xml.Serialization.XmlIgnoreAttribute> al campo o la propiedad y <xref:System.Xml.Serialization.XmlSerializer> omitirán sobre él.

## <a name="see-also"></a>Vea también

- [Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md)
- [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md)
- [Introducción a la serialización XML](introducing-xml-serialization.md)
- [Ejemplos de serialización XML](examples-of-xml-serialization.md)
- [Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserialización de un objeto](how-to-deserialize-an-object.md)
