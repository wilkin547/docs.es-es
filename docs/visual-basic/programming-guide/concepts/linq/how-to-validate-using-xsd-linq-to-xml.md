---
title: Procedimiento para validar con XSD (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
ms.openlocfilehash: fd9931530bde2c47dcc8c7b7363a0d5ffae85b8a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383097"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="4cb33-102">Cómo: validar con XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb33-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="4cb33-103">El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que hacen que sea fácil validar un árbol XML contra un archivo de lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="4cb33-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="4cb33-104">Para obtener más información, vea la documentación del método <xref:System.Xml.Schema.Extensions.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cb33-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cb33-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cb33-105">Example</span></span>  
 <span data-ttu-id="4cb33-106">En el ejemplo siguiente se crea un <xref:System.Xml.Schema.XmlSchemaSet>, a continuación, se validan dos objetos <xref:System.Xml.Linq.XDocument> con el esquema establecido.</span><span class="sxs-lookup"><span data-stu-id="4cb33-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="4cb33-107">Uno de los documentos es válido, el otro no.</span><span class="sxs-lookup"><span data-stu-id="4cb33-107">One of the documents is valid, the other is not.</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim xsdMarkup As XElement = _  
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
            <xsd:element name='Root'>  
                <xsd:complexType>  
                    <xsd:sequence>  
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
                    </xsd:sequence>  
                </xsd:complexType>  
            </xsd:element>  
        </xsd:schema>  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", xsdMarkup.CreateReader)  
  
    Dim doc1 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child2>content1</Child2>  
        </Root>  
  
    Dim doc2 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child3>content1</Child3>  
        </Root>  
  
    Console.WriteLine("Validating doc1")  
    errors = False  
    doc1.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))  
  
    Console.WriteLine()  
    Console.WriteLine("Validating doc2")  
    errors = False  
    doc2.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="4cb33-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4cb33-108">This example produces the following output:</span></span>  
  
```console  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="4cb33-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cb33-109">Example</span></span>  
 <span data-ttu-id="4cb33-110">El siguiente ejemplo valida que el documento XML de [Archivo XML de muestra: clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) sea válido según el esquema de [Archivo XSD de muestra: clientes y pedidos](sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="4cb33-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="4cb33-111">A continuación modifica el documento XML de origen.</span><span class="sxs-lookup"><span data-stu-id="4cb33-111">It then modifies the source XML document.</span></span> <span data-ttu-id="4cb33-112">Cambia el atributo `CustomerID` del primer cliente.</span><span class="sxs-lookup"><span data-stu-id="4cb33-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="4cb33-113">Tras el cambio, los pedidos harán referencia a un cliente que no existe, de forma que el documento XML ya no se validará.</span><span class="sxs-lookup"><span data-stu-id="4cb33-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="4cb33-114">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4cb33-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="4cb33-115">En este ejemplo se usa el siguiente esquema XSD: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md) (Archivo XSD de ejemplo: Clientes y pedidos).</span><span class="sxs-lookup"><span data-stu-id="4cb33-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", "CustomersOrders.xsd")  
  
    Console.WriteLine("Attempting to validate")  
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
  
    Console.WriteLine()  
    ' Modify the source document so that it will not validate.  
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"  
    Console.WriteLine("Attempting to validate after modification")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="4cb33-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4cb33-116">This example produces the following output:</span></span>  
  
```console  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cb33-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cb33-117">See also</span></span>

- <xref:System.Xml.Schema.Extensions.Validate%2A>
- [<span data-ttu-id="4cb33-118">Crear árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb33-118">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
