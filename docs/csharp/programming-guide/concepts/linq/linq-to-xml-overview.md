---
title: Información general de LINQ to XML (C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: dd41d8607ef3f2e6e6be9a1f3964ef0ae937e2ac
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241843"
---
# <a name="linq-to-xml-overview-c"></a>Información general de LINQ to XML (C#)

LINQ to XML proporciona una interfaz de programación XML en memoria que aprovecha .NET Language-Integrated Query (LINQ) Framework. LINQ to XML utiliza las características de .NET y es comparable a una actualizada y rediseñada interfaz de programación XML para el Modelo de objetos de documento (DOM).

XML se ha adoptado ampliamente como un modo de dar formato a datos en diversos contextos. Por ejemplo, puede encontrar XML en la web, en archivos de configuración, en archivos de Microsoft Office Word y en bases de datos.

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es un método actualizado y rediseñado para la programación con XML. Proporciona las funcionalidades de modificación de documentos en memoria del Modelo de objetos de documento (DOM) y es compatible con expresiones de consulta LINQ. Aunque estas expresiones de consulta difieren sintácticamente de XPath, proporcionan una funcionalidad similar.

## <a name="linq-to-xml-developers"></a>Desarrolladores de LINQ to XML

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se dirige a diversos desarrolladores. Para el desarrollador medio que solo desea completar una tarea, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica el código XML al proporcionar una experiencia de consulta similar a SQL. Con un poco de estudio, los programadores pueden aprender a escribir consultas sucintas y eficaces en el lenguaje de programación que prefieran.

Los desarrolladores profesionales pueden usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para aumentar considerablemente su productividad. Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], pueden escribir menos código, que a su vez resulte más expresivo, compacto y eficaz. Pueden usar expresiones de consulta de distintos dominios de datos simultáneamente.

## <a name="what-is-linq-to-xml"></a>¿Qué es LINQ to XML?

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es una interfaz de programación XML en memoria y habilitada para LINQ que permite trabajar con XML desde los lenguajes de programación de .NET.

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se parece a Document Object Model (DOM) en lo que respecta a la inserción del documento XML en la memoria. Puede consultar y modificar el documento; una vez modificado, puede guardarlo en un archivo o serializarlo y enviarlo a través de Internet. Pero [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es diferente de DOM: proporciona un nuevo modelo de objetos más ligero, con el que se trabaja más fácilmente y que aprovecha las características de lenguaje de C#.

La ventaja más importante de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es su integración con Language-Integrated Query (LINQ). Esta integración permite escribir consultas en el documento XML en memoria para recuperar colecciones de elementos y atributos. La capacidad de consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es comparable en cuanto a funcionalidad (aunque no cuanto a sintaxis) a XPath y XQuery. La integración de LINK en C# proporciona una escritura más rápida, comprobación en tiempo de compilación y compatibilidad mejorada con el depurador.

Otra ventaja de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la capacidad de usar los resultados de la consulta como parámetros en constructores de objetos <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>, que habilita un método eficaz para crear árboles XML. Este método, denominado *construcción funcional*, permite que los desarrolladores transformen fácilmente árboles XML de una forma a otra.

Por ejemplo, es posible que tenga un pedido de compra XML típico, como se describe en [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md). Mediante [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], podría ejecutar la siguiente consulta para obtener el valor del atributo de número de pieza relativo a cada elemento del pedido de compra:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

Esto se puede reescribir con formato de sintaxis de método:

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

A modo de ejemplo, imagine que necesita una lista, ordenada por números de pieza, de los elementos con un valor superior a 100 $. Para obtener esta información, podría ejecutar la siguiente consulta:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

De nuevo, esto se puede reescribir con formato de sintaxis de método:

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

Además de estas funcionalidades de LINK, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona una interfaz de programación XML mejorada. Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede:

- Cargar XML a partir de [archivos](how-to-load-xml-from-a-file.md) o [secuencias](how-to-stream-xml-fragments-from-an-xmlreader.md).

- Serializar XML a archivos o secuencias.

- Crear árboles XML desde cero mediante la construcción funcional.

- Realizar consultas de XML con ejes de tipo XPath.

- Manipular el árbol XML en memoria con métodos como <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> y <xref:System.Xml.Linq.XElement.SetValue%2A>.

- Validar árboles XML mediante XSD.

- Usar una combinación de estas características para transformar las formas de los árboles XML.

## <a name="creating-xml-trees"></a>Crear árboles XML

Una de las ventajas más significativas de la programación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la facilidad con que se pueden crear árboles XML. Por ejemplo, para crear un árbol XML pequeño, puede escribir código de la siguiente manera:

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

Para obtener más información, consulte [Crear árboles XML (C#)](./creating-xml-trees-linq-to-xml-2.md).

## <a name="see-also"></a>Vea también

- [Referencia (LINQ to XML)](./reference-linq-to-xml.md)
- [LINQ to XML frente a DOM (C#)](./linq-to-xml-vs-dom.md)
- [LINQ to XML frente a otras tecnologías XML](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
