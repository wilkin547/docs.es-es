---
title: "Generar DataSets fuertemente tipados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Generar DataSets fuertemente tipados
A partir de un esquema XML que cumple con el estándar del lenguaje de definición de esquemas XML \(XSD\), es posible generar un objeto <xref:System.Data.DataSet> fuertemente tipado mediante la herramienta XSD.exe incluida en [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].  
  
 \(Para crear un xsd a partir de las tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [Trabajar con los conjuntos de datos en Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)\).  
  
 En el siguiente código se muestra la sintaxis para generar un **DataSet** con esta herramienta.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 En esta sintaxis, la directiva `/d` indica a la herramienta que genere un **DataSet** y `/l:` le indica el lenguaje que debe utilizar \(por ejemplo, C\# o Visual Basic .NET\).  La directiva `/eld` opcional especifica que puede usar [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] para realizar consultas en el objeto **DataSet.** generado. Esta opción se utiliza cuando también se especifica la opción `/d`.  Para obtener más información, consulta [Consultar DataSets con establecimiento de tipos](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).  La directiva `/n:` opcional indica a la herramienta que genere también un espacio de nombres para el **DataSet** denominado **XSDSchema.Namespace**.  El resultado del comando es XSDSchemaFileName.cs, que se puede compilar y utilizar en una aplicación de ADO.NET.  El código generado puede compilarse como una biblioteca o un módulo.  
  
 En el siguiente código se muestra la sintaxis para compilar el código generado como una biblioteca mediante el compilador de C\# \(csc.exe\).  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 La directiva `/t:` indica a la herramienta que compile en una biblioteca mientras que las directivas `/r:` especifican bibliotecas dependientes necesarias para la compilación.  El resultado del comando es XSDSchemaFileName.dll, que se puede pasar al compilador al compilar una aplicación de ADO.NET con la directiva `/r:`.  
  
 En el siguiente código se muestra la sintaxis para tener acceso al espacio de nombres pasado a XSD.exe en una aplicación de ADO.NET.  
  
```vb  
Imports XSDSchema.Namespace  
  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 En el siguiente ejemplo de código se utiliza un **DataSet** con información de tipos denominado **CustomerDataSet** para cargar una lista de clientes de la base de datos **Northwind**.  Una vez cargados los datos mediante el método **Fill** , el ejemplo recorre en bucle cada cliente de la tabla **Customers** utilizando el objeto **CustomersRow** \(**DataRow**\) con información de tipos.  Esto proporciona acceso directo a la columna **CustomerID**, en lugar de tener acceso a ella mediante **DataColumnCollection**.  
  
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
  
```  
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
  
## Vea también  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [DataSets con establecimiento de tipos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)