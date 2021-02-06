---
description: Más información acerca de cómo generar conjuntos de DataSet fuertemente tipados
title: Generar conjuntos de datos fuertemente tipados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: c69aecc5a0a541c868dac3037c9dd0dbc3fe8383
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652437"
---
# <a name="generating-strongly-typed-datasets"></a>Generar conjuntos de datos fuertemente tipados

Dado un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), puede generar un fuertemente tipado <xref:System.Data.DataSet> mediante la herramienta XSD.exe que se proporciona con el kit de desarrollo de software (SDK) de Windows.  
  
 (Para crear un XSD a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).  
  
 En el código siguiente se muestra la sintaxis para generar un **conjunto** de elementos mediante esta herramienta.  
  
```console  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 En esta sintaxis, la `/d` Directiva indica a la herramienta que genere un **DataSet** y `/l:` indica a la herramienta qué lenguaje usar (por ejemplo, C# o Visual Basic .net). La `/eld` Directiva opcional Especifica que puede utilizar LINQ to DataSet para realizar consultas en el **conjunto de DataSet generado.** Esta opción se utiliza cuando también se especifica la opción `/d`. Para obtener más información, vea [consultar conjuntos de datos con tipo](../querying-typed-datasets.md). La `/n:` Directiva opcional indica a la herramienta que también genere un espacio de nombres para el **DataSet** llamado **XSDSchema. Namespace**. El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET. El código generado puede compilarse como una biblioteca o un módulo.  
  
 En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C# (csc.exe).  
  
```console  
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
  
 En el ejemplo de código siguiente se utiliza un **conjunto** de datos con tipo denominado **CustomerDataSet** para cargar una lista de clientes de la base de datos **Northwind** . Una vez que los datos se cargan con el método **Fill** , el ejemplo recorre en bucle cada cliente de la tabla **Customers** utilizando el objeto **CustomersRow** (**DataRow**) con tipo. Esto proporciona acceso directo a la columna **CustomerID** , en lugar de a través de **DataColumnCollection**.  
  
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
  
 El siguiente es el esquema XML que se usa para el ejemplo:
  
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
- [Objetos DataSet con tipo](typed-datasets.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
