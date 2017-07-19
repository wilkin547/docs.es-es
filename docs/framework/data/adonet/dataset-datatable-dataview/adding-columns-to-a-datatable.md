---
title: "Agregar columnas a la DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Agregar columnas a la DataTable
<xref:System.Data.DataTable> contiene una colección de objetos <xref:System.Data.DataColumn> a los que hace referencia la propiedad **Columns** de la tabla.  Esta colección de columnas, junto con las restricciones que haya, define el esquema, o estructura, de la tabla.  
  
 Los objetos **DataColumn** de una tabla se crean con el constructor **DataColumn** o llamando al método **Add** de la propiedad **Columns** de la tabla, que es una <xref:System.Data.DataColumnCollection>.  El método **Add** acepta argumentos **ColumnName**, **DataType** y **Expression** opcionales y crea una nueva **DataColumn** como miembro de la colección.  También acepta un objeto **DataColumn** existente y lo agrega a la colección y devuelve una referencia a la **DataColumn** agregada si se solicita.  Puesto que los objetos **DataTable** no son específicos de ningún origen de datos, al especificar el tipo de datos de una **DataColumn** se usan los tipos de .NET Framework.  
  
 En el siguiente ejemplo, se agregan cuatro columnas a **DataTable**.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 En el ejemplo, advierta que las propiedades de la columna **CustID** se configuran de manera que no admitan valores **DBNull** y restrinjan los valores para que sean únicos.  Sin embargo, si se define la columna **CustID** como columna de clave principal de la tabla, la propiedad **AllowDBNull** se establecerá automáticamente en **false** y la propiedad **Unique** se establecerá automáticamente en **true**.  Para obtener más información, consulta [Definir claves principales](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Si no se proporciona un nombre para una determinada columna, ésta recibe el nombre predeterminado incremental Column*N,* \(que empieza por "Column1"\), cuando la columna se agrega a la colección **DataColumnCollection**.  Se recomienda evitar la convención de nomenclatura "Column*N*" al proporcionar un nombre de columna, ya que el nombre que se proporcione podría entrar en conflicto con un nombre de columna predeterminado existente en **DataColumnCollection**.  Si el nombre proporcionado ya existe, se inicia una excepción.  
  
 Si está utilizando <xref:System.Xml.XLinq.XElement> como <xref:System.Data.DataColumn.DataType%2A> de una <xref:System.Data.DataColumn> en la <xref:System.Data.DataTable>, la serialización XML no funcionará cuando lea los datos.  Por ejemplo, si escribe un <xref:System.Xml.XmlDocument> utilizando el método `DataTable.WriteXml`, durante la serialización a XML hay un nodo primario adicional en el <xref:System.Xml.XLinq.XElement>.  Para solucionar este problema, utilice el tipo <xref:System.Data.SqlTypes.SqlXml> en lugar de <xref:System.Xml.XLinq.XElement>.  `ReadXml` y `WriteXml` funcionan correctamente con <xref:System.Data.SqlTypes.SqlXml>.  
  
## Vea también  
 <xref:System.Data.DataColumn>   
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataTable>   
 [Definición de esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)