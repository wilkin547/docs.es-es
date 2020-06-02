---
title: Agregar columnas a un objeto DataTable
description: Un objeto DataTable contiene objetos DataColumn a los que hace referencia la propiedad Columns de la tabla. Utilice este código de ejemplo para agregar columnas a una tabla de ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 9d6d21696acd7a6b63cfd6d2ea7e906ec2acd7c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286952"
---
# <a name="adding-columns-to-a-datatable"></a>Agregar columnas a un objeto DataTable
Un <xref:System.Data.DataTable> objeto contiene una colección de <xref:System.Data.DataColumn> objetos a los que hace referencia la propiedad **Columns** de la tabla. Esta colección de columnas, junto con las restricciones que haya, define el esquema, o estructura, de la tabla.  
  
 Puede crear objetos **DataColumn** dentro de una tabla mediante el constructor **DataColumn** o llamando al método **Add** de la propiedad **Columns** de la tabla, que es <xref:System.Data.DataColumnCollection> . El método **Add** acepta argumentos **columnName**, **DataType**y **Expression** opcionales y crea una nueva **DataColumn** como miembro de la colección. También acepta un objeto **DataColumn** existente y lo agrega a la colección y devuelve una referencia a la **DataColumn** agregada si se solicita. Dado que los objetos **DataTable** no son específicos de ningún origen de datos, se usan .NET Framework tipos al especificar el tipo de datos de un objeto **DataColumn**.  
  
 En el ejemplo siguiente se agregan cuatro columnas a **DataTable**.  
  
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
  
 En el ejemplo, observe que las propiedades de la columna **CustID** están configuradas para no permitir valores **DBNull** y para restringir los valores de forma que sean únicos. Sin embargo, si define la columna **CustID** como columna de clave principal de la tabla, la propiedad **AllowDBNull** se establecerá automáticamente en **false** y la propiedad **Unique** se establecerá automáticamente en **true**. Para obtener más información, vea [definir claves principales](defining-primary-keys.md).  
  
> [!CAUTION]
> Si no se proporciona un nombre de columna para una columna, a la columna se le asigna un nombre predeterminado incremental de la columna*N,* empezando por "Column1", cuando se agrega a la **DataColumnCollection**. Se recomienda evitar la Convención de nomenclatura de "Column*N*" al proporcionar un nombre de columna, porque el nombre proporcionado puede entrar en conflicto con un nombre de columna predeterminado existente en **DataColumnCollection**. Si el nombre proporcionado ya existe, se inicia una excepción.  
  
 Si está utilizando <xref:System.Xml.Linq.XElement> como <xref:System.Data.DataColumn.DataType%2A> de una <xref:System.Data.DataColumn> en la <xref:System.Data.DataTable>, la serialización XML no funcionará cuando lea los datos. Por ejemplo, si escribe un <xref:System.Xml.XmlDocument> utilizando el método `DataTable.WriteXml`, durante la serialización a XML hay un nodo primario adicional en el <xref:System.Xml.Linq.XElement>. Para solucionar este problema, utilice el tipo <xref:System.Data.SqlTypes.SqlXml> en lugar de <xref:System.Xml.Linq.XElement>. `ReadXml` y `WriteXml` funcionan correctamente con <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [Definición del esquema de DataTable](datatable-schema-definition.md)
- [Objetos DataTable](datatables.md)
- [Información general de ADO.NET](../ado-net-overview.md)
