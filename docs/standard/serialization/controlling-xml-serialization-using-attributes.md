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
# <a name="controlling-xml-serialization-using-attributes"></a><span data-ttu-id="c27b8-103">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="c27b8-103">Controlling XML Serialization Using Attributes</span></span>

<span data-ttu-id="c27b8-104">Los atributos se pueden utilizar para controlar la serialización XML de un objeto o crear una secuencia XML alternativa a partir del mismo conjunto de clases.</span><span class="sxs-lookup"><span data-stu-id="c27b8-104">Attributes can be used to control the XML serialization of an object or to create an alternate XML stream from the same set of classes.</span></span> <span data-ttu-id="c27b8-105">Para obtener más información sobre la creación de una secuencia XML alternativa vea [Procedimiento para especificar un nombre de elemento alternativo para una secuencia XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="c27b8-105">For more details about creating an alternate XML stream, see [How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c27b8-106">Si el código XML generado se ajusta a la sección 5 del documento [Protocolo simple de acceso a objetos (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), del Consorcio WWC (W3C), use los atributos enumerados en [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c27b8-106">If the XML generated must conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), use the attributes listed in [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>

<span data-ttu-id="c27b8-107">La clase o nombre de miembro determina, de forma predeterminada, un nombre del elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c27b8-107">By default, an XML element name is determined by the class or member name.</span></span> <span data-ttu-id="c27b8-108">En una clase simple denominada `Book`, un campo denominado `ISBN` generará una etiqueta del elemento XML \<ISBN> como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-108">In a simple class named `Book`, a field named `ISBN` will produce an XML element tag \<ISBN>, as shown in the following example.</span></span>

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

<span data-ttu-id="c27b8-109">Se puede cambiar este comportamiento predeterminado si desea dar un nuevo nombre al elemento.</span><span class="sxs-lookup"><span data-stu-id="c27b8-109">This default behavior can be changed if you want to give the element a new name.</span></span> <span data-ttu-id="c27b8-110">El código siguiente muestra cómo un atributo habilita esto estableciendo la propiedad <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> de <xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c27b8-110">The following code shows how an attribute enables this by setting the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> property of a <xref:System.Xml.Serialization.XmlElementAttribute>.</span></span>

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

<span data-ttu-id="c27b8-111">Para obtener más información sobre atributos, vea [Atributos](../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="c27b8-111">For more information about attributes, see [Attributes](../../../docs/standard/attributes/index.md).</span></span> <span data-ttu-id="c27b8-112">Para obtener una lista de atributos que controlan la serialización XML, vea [Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c27b8-112">For a list of attributes that control XML serialization, see [Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md).</span></span>

## <a name="controlling-array-serialization"></a><span data-ttu-id="c27b8-113">Controlar la serialización de la matriz</span><span class="sxs-lookup"><span data-stu-id="c27b8-113">Controlling Array Serialization</span></span>

<span data-ttu-id="c27b8-114">Los atributos <xref:System.Xml.Serialization.XmlArrayAttribute> y <xref:System.Xml.Serialization.XmlArrayItemAttribute> están diseñados para controlar la serialización de las matrices.</span><span class="sxs-lookup"><span data-stu-id="c27b8-114">The <xref:System.Xml.Serialization.XmlArrayAttribute> and the <xref:System.Xml.Serialization.XmlArrayItemAttribute> attributes are designed to control the serialization of arrays.</span></span> <span data-ttu-id="c27b8-115">Con estos atributos, puede controlar el nombre de elemento, el espacio de nombres y el tipo de datos del esquema XML (XSD) (como se define en el documento de World Wide Web Consortium [www.w3.org] titulado "Esquema XML parte 2: tipos de datos").</span><span class="sxs-lookup"><span data-stu-id="c27b8-115">Using these attributes, you can control the element name, namespace, and XML Schema (XSD) data type (as defined in the World Wide Web Consortium [www.w3.org] document titled "XML Schema Part 2: Datatypes").</span></span> <span data-ttu-id="c27b8-116">También puede especificar los tipos que pueden estar incluidos en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-116">You can also specify the types that can be included in an array.</span></span>

<span data-ttu-id="c27b8-117"><xref:System.Xml.Serialization.XmlArrayAttribute> determinará las propiedades del elemento envolvente XML que resulta cuando se serializa una matriz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-117">The <xref:System.Xml.Serialization.XmlArrayAttribute> will determine the properties of the enclosing XML element that results when an array is serialized.</span></span> <span data-ttu-id="c27b8-118">Por ejemplo, de forma predeterminada, serializar la matriz siguiente producirá un elemento XML denominado `Employees`.</span><span class="sxs-lookup"><span data-stu-id="c27b8-118">For example, by default, serializing the array below will result in an XML element named `Employees`.</span></span> <span data-ttu-id="c27b8-119">El elemento `Employees` contendrá una serie de elementos denominados según el tipo de matriz `Employee`.</span><span class="sxs-lookup"><span data-stu-id="c27b8-119">The `Employees` element will contain a series of elements named after the array type `Employee`.</span></span>

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

<span data-ttu-id="c27b8-120">Una instancia serializada se podría parecer a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-120">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

<span data-ttu-id="c27b8-121">Aplicando <xref:System.Xml.Serialization.XmlArrayAttribute>, puede cambiar el nombre del elemento XML, como sigue.</span><span class="sxs-lookup"><span data-stu-id="c27b8-121">By applying a <xref:System.Xml.Serialization.XmlArrayAttribute>, you can change the name of the XML element, as follows.</span></span>

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

<span data-ttu-id="c27b8-122">El XML resultante puede parecerse a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-122">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<span data-ttu-id="c27b8-123"><xref:System.Xml.Serialization.XmlArrayItemAttribute>, por otro lado, controla cómo se serializan los elementos contenidos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-123">The <xref:System.Xml.Serialization.XmlArrayItemAttribute>, on the other hand, controls how the items contained in the array are serialized.</span></span> <span data-ttu-id="c27b8-124">Observe que el atributo se aplica al campo que devuelve la matriz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-124">Note that the attribute is applied to the field returning the array.</span></span>

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

<span data-ttu-id="c27b8-125">El XML resultante puede parecerse a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-125">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a><span data-ttu-id="c27b8-126">Serializar las clases derivadas</span><span class="sxs-lookup"><span data-stu-id="c27b8-126">Serializing Derived Classes</span></span>

<span data-ttu-id="c27b8-127">Otro uso de <xref:System.Xml.Serialization.XmlArrayItemAttribute> es permitir la serialización de clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="c27b8-127">Another use of the <xref:System.Xml.Serialization.XmlArrayItemAttribute> is to allow the serialization of derived classes.</span></span> <span data-ttu-id="c27b8-128">Por ejemplo, otra clase denominada `Manager` que deriva de `Employee` se puede agregar al ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c27b8-128">For example, another class named `Manager` that derives from `Employee` can be added to the previous example.</span></span> <span data-ttu-id="c27b8-129">Si no aplica <xref:System.Xml.Serialization.XmlArrayItemAttribute>, se producirá un error en el código en tiempo de ejecución porque no se reconocerá el tipo de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c27b8-129">If you do not apply the <xref:System.Xml.Serialization.XmlArrayItemAttribute>, the code will fail at run time because the derived class type will not be recognized.</span></span> <span data-ttu-id="c27b8-130">Para solucionar esto, aplique dos veces el atributo, estableciendo la propiedad <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> cada vez, para cada tipo aceptable (base y derivado).</span><span class="sxs-lookup"><span data-stu-id="c27b8-130">To remedy this, apply the attribute twice, each time setting the <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> property for each acceptable type (base and derived).</span></span>

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

<span data-ttu-id="c27b8-131">Una instancia serializada se podría parecer a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-131">A serialized instance might resemble the following.</span></span>

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

## <a name="serializing-an-array-as-a-sequence-of-elements"></a><span data-ttu-id="c27b8-132">Serializar una matriz como una secuencia de elementos</span><span class="sxs-lookup"><span data-stu-id="c27b8-132">Serializing an Array as a Sequence of Elements</span></span>

<span data-ttu-id="c27b8-133">También puede serializar una matriz como una secuencia plana de elementos XML aplicando <xref:System.Xml.Serialization.XmlElementAttribute> al campo que devuelve la matriz como sigue.</span><span class="sxs-lookup"><span data-stu-id="c27b8-133">You can also serialize an array as a flat sequence of XML elements by applying a <xref:System.Xml.Serialization.XmlElementAttribute> to the field returning the array as follows.</span></span>

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

<span data-ttu-id="c27b8-134">Una instancia serializada se podría parecer a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-134">A serialized instance might resemble the following.</span></span>

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

<span data-ttu-id="c27b8-135">Otra manera de diferenciar las dos secuencias XML es utilizar la herramienta de definición de esquemas XML para generar los archivos de documento de esquema XML (XSD) a partir del código compilado.</span><span class="sxs-lookup"><span data-stu-id="c27b8-135">Another way to differentiate the two XML streams is to use the XML Schema Definition tool to generate the XML Schema (XSD) document files from the compiled code.</span></span> <span data-ttu-id="c27b8-136">(Para obtener más información sobre el uso de la herramienta, vea [La herramienta de definición de esquema XML y serialización XML](the-xml-schema-definition-tool-and-xml-serialization.md)). Cuando no se aplica ningún atributo al campo, el esquema describe el elemento de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-136">(For more details on using the tool, see [The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md).) When no attribute is applied to the field, the schema describes the element in the following manner.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

<span data-ttu-id="c27b8-137">Cuando <xref:System.Xml.Serialization.XmlElementAttribute> se aplica al campo, el esquema resultante describe el elemento como sigue.</span><span class="sxs-lookup"><span data-stu-id="c27b8-137">When the <xref:System.Xml.Serialization.XmlElementAttribute> is applied to the field, the resulting schema describes the element as follows.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a><span data-ttu-id="c27b8-138">Serializar un ArrayList</span><span class="sxs-lookup"><span data-stu-id="c27b8-138">Serializing an ArrayList</span></span>

<span data-ttu-id="c27b8-139">La clase <xref:System.Collections.ArrayList> puede contener una colección de objetos diversos.</span><span class="sxs-lookup"><span data-stu-id="c27b8-139">The <xref:System.Collections.ArrayList> class can contain a collection of diverse objects.</span></span> <span data-ttu-id="c27b8-140">Además puede utilizar <xref:System.Collections.ArrayList> tantas veces como utiliza la matriz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-140">You can therefore use a <xref:System.Collections.ArrayList> much as you use an array.</span></span> <span data-ttu-id="c27b8-141">En lugar de crear un campo que devuelve una matriz de objetos escritos, sin embargo, puede crear un campo que devuelve un <xref:System.Collections.ArrayList>único.</span><span class="sxs-lookup"><span data-stu-id="c27b8-141">Instead of creating a field that returns an array of typed objects, however, you can create a field that returns a single <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="c27b8-142">Sin embargo, al igual que con las matrices, debe informar a<xref:System.Xml.Serialization.XmlSerializer> de los tipos de objetos <xref:System.Collections.ArrayList> que contiene.</span><span class="sxs-lookup"><span data-stu-id="c27b8-142">However, as with arrays, you must inform the <xref:System.Xml.Serialization.XmlSerializer> of the types of objects the <xref:System.Collections.ArrayList> contains.</span></span> <span data-ttu-id="c27b8-143">Para lograr esto, asigne varias instancias de <xref:System.Xml.Serialization.XmlElementAttribute> al campo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c27b8-143">To accomplish this, assign multiple instances of the <xref:System.Xml.Serialization.XmlElementAttribute> to the field, as shown in the following example.</span></span>

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

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a><span data-ttu-id="c27b8-144">Controle la serialización de clases utilizando XmlRootAttribute y XmlTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="c27b8-144">Controlling Serialization of Classes Using XmlRootAttribute and XmlTypeAttribute</span></span>

<span data-ttu-id="c27b8-145">Existen dos atributos que pueden aplicarse a la clase (y solamente una clase): <xref:System.Xml.Serialization.XmlRootAttribute> y <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c27b8-145">There are two attributes that can be applied to a class (and only a class): <xref:System.Xml.Serialization.XmlRootAttribute> and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span> <span data-ttu-id="c27b8-146">Estos atributos son muy similares.</span><span class="sxs-lookup"><span data-stu-id="c27b8-146">These attributes are very similar.</span></span> <span data-ttu-id="c27b8-147"><xref:System.Xml.Serialization.XmlRootAttribute> se puede aplicar a solo una clase: la clase que, cuando se serializa, representa el elemento de apertura y cierre del documento XML, en otras palabras, el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-147">The <xref:System.Xml.Serialization.XmlRootAttribute> can be applied to only one class: the class that, when serialized, represents the XML document's opening and closing element—in other words, the root element.</span></span> <span data-ttu-id="c27b8-148"><xref:System.Xml.Serialization.XmlTypeAttribute>, por otro lado, se puede aplicar a cualquier clase, incluso a la clase raíz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-148">The <xref:System.Xml.Serialization.XmlTypeAttribute>, on the other hand, can be applied to any class, including the root class.</span></span>

<span data-ttu-id="c27b8-149">Por ejemplo, en los ejemplos anteriores, la clase `Group` es la clase raíz y todos sus campos públicos y propiedades se vuelven elementos XML situados en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="c27b8-149">For example, in the previous examples, the `Group` class is the root class, and all its public fields and properties become the XML elements found in the XML document.</span></span> <span data-ttu-id="c27b8-150">Además, solo puede haber una clase de raíz.</span><span class="sxs-lookup"><span data-stu-id="c27b8-150">Therefore, there can be only one root class.</span></span> <span data-ttu-id="c27b8-151">Aplicando <xref:System.Xml.Serialization.XmlRootAttribute>, puede controlar la secuencia XML generada por <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c27b8-151">By applying the <xref:System.Xml.Serialization.XmlRootAttribute>, you can control the XML stream generated by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="c27b8-152">Por ejemplo, puede cambiar el nombre de elemento y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c27b8-152">For example, you can change the element name and namespace.</span></span>

<span data-ttu-id="c27b8-153"><xref:System.Xml.Serialization.XmlTypeAttribute> le permite controlar el esquema del XML generado.</span><span class="sxs-lookup"><span data-stu-id="c27b8-153">The <xref:System.Xml.Serialization.XmlTypeAttribute> allows you to control the schema of the generated XML.</span></span> <span data-ttu-id="c27b8-154">Esta función es útil si se necesita publicar el esquema a través de un servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="c27b8-154">This capability is useful when you need to publish the schema through an XML Web service.</span></span> <span data-ttu-id="c27b8-155">En el siguiente ejemplo, se aplica <xref:System.Xml.Serialization.XmlTypeAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="c27b8-155">The following example applies both the <xref:System.Xml.Serialization.XmlTypeAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the same class.</span></span>

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

<span data-ttu-id="c27b8-156">Si esta clase está compilada, y la herramienta de definición de esquemas XML se utiliza para generar su esquema, encontraría el XML siguiente que describe `Group`.</span><span class="sxs-lookup"><span data-stu-id="c27b8-156">If this class is compiled, and the XML Schema Definition tool is used to generate its schema, you would find the following XML describing `Group`.</span></span>

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

<span data-ttu-id="c27b8-157">En contraste, si fuera serializar una instancia de la clase, solo `NewGroupName` se buscarían en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="c27b8-157">In contrast, if you were to serialize an instance of the class, only `NewGroupName` would be found in the XML document.</span></span>

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a><span data-ttu-id="c27b8-158">Evitar la serialización con XmlIgnoreAttribute</span><span class="sxs-lookup"><span data-stu-id="c27b8-158">Preventing Serialization with the XmlIgnoreAttribute</span></span>

<span data-ttu-id="c27b8-159">Podrían darse situaciones en las que una propiedad pública o el campo no necesite ser serializado.</span><span class="sxs-lookup"><span data-stu-id="c27b8-159">There might be situations when a public property or field does not need to be serialized.</span></span> <span data-ttu-id="c27b8-160">Por ejemplo, un campo o propiedad se puede utilizar para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c27b8-160">For example, a field or property could be used to contain metadata.</span></span> <span data-ttu-id="c27b8-161">En casos como éste, aplique <xref:System.Xml.Serialization.XmlIgnoreAttribute> al campo o la propiedad y <xref:System.Xml.Serialization.XmlSerializer> omitirán sobre él.</span><span class="sxs-lookup"><span data-stu-id="c27b8-161">In such cases, apply the <xref:System.Xml.Serialization.XmlIgnoreAttribute> to the field or property and the <xref:System.Xml.Serialization.XmlSerializer> will skip over it.</span></span>

## <a name="see-also"></a><span data-ttu-id="c27b8-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="c27b8-162">See also</span></span>

- [<span data-ttu-id="c27b8-163">Atributos que controlan la serialización XML</span><span class="sxs-lookup"><span data-stu-id="c27b8-163">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="c27b8-164">Atributos que controlan la serialización SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="c27b8-164">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="c27b8-165">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="c27b8-165">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="c27b8-166">Ejemplos de serialización XML</span><span class="sxs-lookup"><span data-stu-id="c27b8-166">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)
- [<span data-ttu-id="c27b8-167">Cómo: Especificar un nombre de elemento alternativo para una secuencia XML</span><span class="sxs-lookup"><span data-stu-id="c27b8-167">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="c27b8-168">Cómo: Serialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="c27b8-168">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="c27b8-169">Cómo: Deserialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="c27b8-169">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
