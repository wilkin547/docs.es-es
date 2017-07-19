---
title: "Restricciones de DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Restricciones de DataTable
Se pueden utilizar restricciones para exigir restricciones sobre los datos de un objeto <xref:System.Data.DataTable> con el fin de mantener la integridad de los datos.  Una restricción es una regla automática que se aplica a una columna, o a varias columnas relacionadas, que determina cómo proceder cuando se modifica de alguna manera el valor de una fila.  Las restricciones se exigen cuando la propiedad  `System.Data.DataSet.EnforceConstraints` del <xref:System.Data.DataSet> es **true**.  Para ver un ejemplo de código que muestre cómo establecer la propiedad `EnforceConstraints`, vea el tema de referencia <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 Existen dos tipos de restricciones en ADO.NET: <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>.  De forma predeterminada, las dos restricciones se crean automáticamente al crear una relación entre dos o más tablas agregando <xref:System.Data.DataRelation> al **DataSet**.  Sin embargo, se puede deshabilitar este comportamiento especificando **createConstraints** \= **false** al crear la relación.  
  
## ForeignKeyConstraint  
 **ForeignKeyConstraint** exige reglas sobre cómo se propagan las actualizaciones y eliminaciones a las tablas relacionadas.  Por ejemplo, si se actualiza o elimina el valor de una fila de una tabla y el mismo valor también se utiliza en una o varias tablas relacionadas, **ForeignKeyConstraint** determinará qué sucede en las tablas relacionadas.  
  
 Las propiedades <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> y <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> de **ForeignKeyConstraint** definen la acción que se ha de realizar cuando el usuario intente eliminar o actualizar una fila en una tabla relacionada.  En la tabla siguiente se describen las distintas configuraciones disponibles para las propiedades **DeleteRule** y **UpdateRule** de **ForeignKeyConstraint**  
  
|Establecimiento de reglas|Descripción|  
|-------------------------------|-----------------|  
|**Cascade**|Elimina o actualiza las filas relacionadas.|  
|**SetNull**|Establece los valores de las filas relacionadas en **DBNull**.|  
|**SetDefault**|Establece los valores de las filas relacionadas en el valor predeterminado.|  
|**Ninguna**|No realiza ninguna acción en las filas relacionadas.  Este es el valor predeterminado.|  
  
 **ForeignKeyConstraint** puede restringir, además de propagar, los cambios en las columnas relacionadas.  Dependiendo de las propiedades establecidas para la **ForeignKeyConstraint** de una columna, y si la propiedad **EnforceConstraints** del **DataSet** es **true**, realizar ciertas operaciones en la fila primaria generará una excepción.  Por ejemplo, si la propiedad **DeleteRule** de **ForeignKeyConstraint** es **None**, una fila primaria no se puede eliminar si tiene filas secundarias.  
  
 Se puede crear una restricción de clave externa entre columnas individuales o entre una matriz de columnas utilizando el constructor **ForeignKeyConstraint.** Pase el objeto **ForeignKeyConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es una **ConstraintCollection**.  También puede pasar argumentos de constructor a varias sobrecargas del método **Add** de **ConstraintCollection** para crear una **ForeignKeyConstraint.**  
  
 Al crear una **ForeignKeyConstraint**, se pueden pasar los valores **DeleteRule** y **UpdateRule** al constructor como argumentos, o se pueden configurar como propiedades, como en el ejemplo siguiente \(en que el valor **DeleteRule** se establece como **None**\).  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### AcceptRejectRule  
 Los cambios realizados en filas se pueden aceptar con el método **AcceptChanges** o cancelar con el método **RejectChanges** de **DataSet**, **DataTable** o **DataRow**.  Si un **DataSet** contiene **ForeignKeyConstraints**, al invocar los métodos **AcceptChanges** o **RejectChanges** se exige **AcceptRejectRule**.  La propiedad **AcceptRejectRule** de **ForeignKeyConstraint** determina qué acción se tomará en las filas secundarias cuando se llame a **AcceptChanges** o **RejectChanges** en la fila primaria.  
  
 En la siguiente tabla se incluyen los valores disponibles para **AcceptRejectRule**.  
  
|Establecimiento de reglas|Descripción|  
|-------------------------------|-----------------|  
|**Cascade**|Acepta o rechaza los cambios en filas secundarias.|  
|**Ninguna**|No realiza ninguna acción en las filas secundarias.  Este es el valor predeterminado.|  
  
### Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Data.ForeignKeyConstraint>, se establecen varias de sus propiedades, incluida la <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, y se añade a la <xref:System.Data.ConstraintCollection> de un objeto <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## UniqueConstraint  
 El objeto **UniqueConstraint**, que se puede asignar a una sola columna o a una matriz de columnas de una **DataTable**, garantiza que todos los datos de las columnas especificadas son únicos en cada fila.  Se puede crear una restricción única para una columna o matriz de columnas con el constructor **UniqueConstraint**.  Pase el objeto **UniqueConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es una **ConstraintCollection**.  También puede pasar argumentos de constructor a varias sobrecargas del método **Add** de una **ConstraintCollection** para crear una **UniqueConstraint.** Al crear una **UniqueConstraint** para una columna o columnas, se puede especificar opcionalmente si la columna o columnas son una clave principal.  
  
 También se puede crear una restricción única para una sola columna estableciendo su propiedad **Unique** en **true**.  Por otra parte, si se establece la propiedad **Unique** de una sola columna en **false** se quita cualquier restricción única que pudiera existir.  Si se define una o varias columnas como clave principal de una tabla se creará automáticamente una restricción única para la columna o columnas especificadas.  Si quita una columna mediante la propiedad **PrimaryKey** de una **DataTable**, se quita la **UniqueConstraint**.  
  
 En el ejemplo siguiente se crea una **UniqueConstraint** para dos columnas de una **DataTable**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## Vea también  
 <xref:System.Data.DataRelation>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.ForeignKeyConstraint>   
 <xref:System.Data.UniqueConstraint>   
 [Definición de esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)