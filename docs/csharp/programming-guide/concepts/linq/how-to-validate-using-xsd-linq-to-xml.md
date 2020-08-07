---
title: Procedimiento para realizar validaciones con XSD (LINQ to XML) (C#)
description: Aprenda a validar un árbol XML con un archivo de lenguaje de definición de esquemas XML (XSD). Vea ejemplos de código y examine recursos adicionales.
ms.date: 07/20/2015
ms.assetid: 6a7f83a9-2d74-4c2b-8417-0a8595879516
ms.openlocfilehash: 3b4d2137d511efbe20e4d31ad27e4975d5444ec9
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302638"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-c"></a><span data-ttu-id="7a06b-104">Procedimiento para realizar validaciones con XSD (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7a06b-104">How to validate using XSD (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7a06b-105">El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que hacen que sea fácil validar un árbol XML contra un archivo de lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="7a06b-105">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="7a06b-106">Para obtener más información, vea la documentación del método <xref:System.Xml.Schema.Extensions.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a06b-106">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a06b-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a06b-107">Example</span></span>  
 <span data-ttu-id="7a06b-108">En el ejemplo siguiente se crea un <xref:System.Xml.Schema.XmlSchemaSet>, a continuación, se validan dos objetos <xref:System.Xml.Linq.XDocument> con el esquema establecido.</span><span class="sxs-lookup"><span data-stu-id="7a06b-108">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="7a06b-109">Uno de los documentos es válido, el otro no.</span><span class="sxs-lookup"><span data-stu-id="7a06b-109">One of the documents is valid, the other is not.</span></span>  
  
```csharp  
string xsdMarkup =  
    @"<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
       <xsd:element name='Root'>  
        <xsd:complexType>  
         <xsd:sequence>  
          <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
          <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
         </xsd:sequence>  
        </xsd:complexType>  
       </xsd:element>  
      </xsd:schema>";  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", XmlReader.Create(new StringReader(xsdMarkup)));  
  
XDocument doc1 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child2", "content1")  
    )  
);  
  
XDocument doc2 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child3", "content1")  
    )  
);  
  
Console.WriteLine("Validating doc1");  
bool errors = false;  
doc1.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc1 {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
Console.WriteLine("Validating doc2");  
errors = false;  
doc2.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc2 {0}", errors ? "did not validate" : "validated");  
```  
  
 <span data-ttu-id="7a06b-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7a06b-110">This example produces the following output:</span></span>  
  
```output  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="7a06b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a06b-111">Example</span></span>  
 <span data-ttu-id="7a06b-112">El siguiente ejemplo valida que el documento XML de [Archivo XML de muestra: clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) sea válido según el esquema de [Archivo XSD de muestra: clientes y pedidos](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="7a06b-112">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) is valid per the schema from [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="7a06b-113">A continuación modifica el documento XML de origen.</span><span class="sxs-lookup"><span data-stu-id="7a06b-113">It then modifies the source XML document.</span></span> <span data-ttu-id="7a06b-114">Cambia el atributo `CustomerID` del primer cliente.</span><span class="sxs-lookup"><span data-stu-id="7a06b-114">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="7a06b-115">Tras el cambio, los pedidos harán referencia a un cliente que no existe, de forma que el documento XML ya no se validará.</span><span class="sxs-lookup"><span data-stu-id="7a06b-115">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="7a06b-116">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="7a06b-116">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="7a06b-117">En este ejemplo se usa el siguiente esquema XSD: [Archivo XSD de ejemplo: Clientes y pedidos](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="7a06b-117">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.WriteLine("Attempting to validate");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
// Modify the source document so that it will not validate.  
custOrdDoc.Root.Element("Orders").Element("Order").Element("CustomerID").Value = "AAAAA";  
Console.WriteLine("Attempting to validate after modification");  
errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
```  
  
 <span data-ttu-id="7a06b-118">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7a06b-118">This example produces the following output:</span></span>  
  
```output  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a06b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a06b-119">See also</span></span>

- <xref:System.Xml.Schema.Extensions.Validate%2A>
- [<span data-ttu-id="7a06b-120">Crear árboles XML en C# </span><span class="sxs-lookup"><span data-stu-id="7a06b-120">Creating XML Trees (C#)</span></span>](creating-xml-trees-linq-to-xml-2.md)
