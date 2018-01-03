---
title: Generar conjuntos de datos fuertemente tipados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 867c6f5fa918b0886d8d618e89c62201cd92b213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="generating-strongly-typed-datasets"></a>Generar conjuntos de datos fuertemente tipados
A partir de un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML (XSD), es posible generar un objeto <xref:System.Data.DataSet> fuertemente tipado mediante la herramienta XSD.exe incluida en [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].  
  
 (Para crear un xsd a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
 El código siguiente muestra la sintaxis para generar un **conjunto de datos** con esta herramienta.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 En esta sintaxis, la `/d` directiva indica a la herramienta que genere un **conjunto de datos**y el `/l:` indica a la herramienta lenguaje que debe utilizar (por ejemplo, C# o Visual Basic. NET). Opcional `/eld` directiva especifica que se puede utilizar [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] consultas en los botones generados **conjunto de datos.** Esta opción se utiliza cuando también se especifica la opción `/d`. Para obtener más información, consulte [consultar conjuntos de datos con tipo](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). Opcional `/n:` directiva indica a la herramienta que genere también un espacio de nombres para el **conjunto de datos** llama **XSDSchema.Namespace**. El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET. El código generado puede compilarse como una biblioteca o un módulo.  
  
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
  
 En el ejemplo de código siguiente se utiliza un **conjunto de datos** denominado **CustomerDataSet** para cargar una lista de los clientes de la **Northwind** base de datos. Una vez que los datos se cargan con la **rellenar** método, el ejemplo recorre cada cliente de la **clientes** con el tipo de tabla **CustomersRow** ( **DataRow**) objeto. Esto proporciona acceso directo a la **CustomerID** columna, en lugar de a través del **DataColumnCollection**.  
  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Objetos DataSet con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
