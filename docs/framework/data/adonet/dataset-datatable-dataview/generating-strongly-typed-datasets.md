---
title: Generar conjuntos de datos fuertemente tipados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: d0a22a4ec4ed508a06e385d954a8ed5b9e9ff6a9
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825594"
---
# <a name="generating-strongly-typed-datasets"></a>Generar conjuntos de datos fuertemente tipados
A partir de un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), es posible generar un objeto <xref:System.Data.DataSet> fuertemente tipado mediante la herramienta XSD.exe incluida en [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].  
  
 (Para crear un xsd a partir de las tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con objetos DataSet en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).  
  
 El código siguiente muestra la sintaxis para generar un **DataSet** con esta herramienta.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 En esta sintaxis, el `/d` directiva indica a la herramienta para generar un **DataSet**y el `/l:` indica a la herramienta de lenguaje que debe utilizar (por ejemplo, C# o Visual Basic. NET). El elemento opcional `/eld` directiva especifica que se puede utilizar [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] para consultar contra generado **conjunto de datos.** Esta opción se utiliza cuando también se especifica la opción `/d`. Para obtener más información, consulte [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). Opcional `/n:` directiva indica a la herramienta que genere también un espacio de nombres para el **DataSet** llamado **XSDSchema.Namespace**. El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET. El código generado puede compilarse como una biblioteca o un módulo.  
  
 En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C# (csc.exe).  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 La directiva `/t:` indica a la herramienta que compile en una biblioteca mientras que las directivas `/r:` especifican bibliotecas dependientes necesarias para la compilación. El resultado del comando es XSDSchemaFileName.dll, que se puede pasar al compilador al compilar una aplicación de ADO.NET con la directiva `/r:`.  
  
 En el siguiente código se muestra la sintaxis para tener acceso al espacio de nombres pasado a XSD.exe en una aplicación de ADO.NET.  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 En el ejemplo de código siguiente se utiliza un **DataSet** denominado **CustomerDataSet** para cargar una lista de clientes desde el **Northwind** base de datos. Una vez cargados los datos mediante el **rellenar** método, el ejemplo recorre en bucle cada cliente en el **clientes** con el tipo de tabla **CustomersRow** ( **DataRow**) objetos. Esto proporciona acceso directo a la **CustomerID** columna, en lugar de a través del **DataColumnCollection**.  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 A continuación se muestra el esquema XML utilizado para el ejemplo.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Objetos DataSet con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
