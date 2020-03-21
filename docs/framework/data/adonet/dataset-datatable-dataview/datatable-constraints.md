---
title: Restricciones de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151291"
---
# <a name="datatable-constraints"></a>Restricciones de DataTable
Se pueden utilizar restricciones para exigir restricciones sobre los datos de un objeto <xref:System.Data.DataTable> con el fin de mantener la integridad de los datos. Una restricción es una regla automática que se aplica a una columna, o a varias columnas relacionadas, que determina cómo proceder cuando se modifica de alguna manera el valor de una fila. Las restricciones se `System.Data.DataSet.EnforceConstraints` aplican cuando <xref:System.Data.DataSet> la propiedad de la es **true**. Para ver un ejemplo de código que muestre cómo establecer la propiedad `EnforceConstraints`, vea el tema de referencia <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 Existen dos tipos de restricciones en ADO.NET: <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>. De forma predeterminada, ambas restricciones se crean automáticamente al crear <xref:System.Data.DataRelation> una relación entre dos o más tablas agregando un conjunto de **datos**. Sin embargo, puede deshabilitar este comportamiento especificando **createConstraints** = **false** al crear la relación.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 Un **ForeignKeyConstraint** aplica reglas sobre cómo se propagan las actualizaciones y eliminaciones a las tablas relacionadas. Por ejemplo, si se actualiza o elimina un valor de una fila de una tabla y ese mismo valor también se usa en una o varias tablas relacionadas, **ForeignKeyConstraint** determina lo que sucede en las tablas relacionadas.  
  
 Las <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> propiedades y de **ForeignKeyConstraint** definen la acción que se debe realizar cuando el usuario intenta eliminar o actualizar una fila de una tabla relacionada. En la tabla siguiente se describen las diferentes opciones disponibles para las propiedades **DeleteRule** y **UpdateRule** de **ForeignKeyConstraint**.  
  
|Establecimiento de reglas|Descripción|  
|------------------|-----------------|  
|**Cascada**|Elimina o actualiza las filas relacionadas.|  
|**SetNull**|Establezca valores en filas relacionadas en **DBNull**.|  
|**SetDefault**|Establece los valores de las filas relacionadas en el valor predeterminado.|  
|**Ninguno**|No realiza ninguna acción en las filas relacionadas. Este es el valor predeterminado.|  
  
 Un **ForeignKeyConstraint** puede restringir, así como propagar, los cambios a las columnas relacionadas. Dependiendo de las propiedades establecidas para **el ForeignKeyConstraint** de una columna, si el **EnforceConstraints** propiedad de la **DataSet** es **true**, realizar ciertas operaciones en la fila primaria dará lugar a una excepción. Por ejemplo, si la propiedad **DeleteRule** de **ForeignKeyConstraint** es **None**, no se puede eliminar una fila primaria si tiene filas secundarias.  
  
 Puede crear una restricción de clave externa entre columnas individuales o entre una matriz de columnas mediante el **constructor ForeignKeyConstraint.** Pase el objeto **ForeignKeyConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es **ConstraintCollection**. También puede pasar argumentos de constructor a varias sobrecargas de la **Add** método de un **ConstraintCollection** para crear un **ForeignKeyConstraint**.  
  
 Al crear un **ForeignKeyConstraint**, puede pasar los valores **DeleteRule** y **UpdateRule** al constructor como argumentos, o puede establecerlos como propiedades como en el ejemplo siguiente (donde el valor **DeleteRule** se establece en **None**).  
  
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
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  
 Los cambios en las filas se pueden aceptar mediante el método **AcceptChanges** o cancelarse mediante el método **RejectChanges** de **DataSet**, **DataTable**o **DataRow**. Cuando un **DataSet** contiene **ForeignKeyConstraints**, invocar los métodos **AcceptChanges** o **RejectChanges** aplica el **acceptRejectRule**. La propiedad **AcceptRejectRule** de **ForeignKeyConstraint** determina qué acción se realizará en las filas secundarias cuando se llame **a AcceptChanges** o **RejectChanges** en la fila primaria.  
  
 En la tabla siguiente se enumeran los valores disponibles para **AcceptRejectRule**.  
  
|Establecimiento de reglas|Descripción|  
|------------------|-----------------|  
|**Cascada**|Acepta o rechaza los cambios en filas secundarias.|  
|**Ninguno**|No realiza ninguna acción en las filas secundarias. Este es el valor predeterminado.|  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Data.ForeignKeyConstraint>, se establecen varias de sus propiedades, incluida la <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, y se añade a la <xref:System.Data.ConstraintCollection> de un objeto <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 El objeto **UniqueConstraint,** que se puede asignar a una sola columna o a una matriz de columnas en una **DataTable**, garantiza que todos los datos de la columna o columnas especificadas sean únicos por fila. Puede crear una restricción única para una columna o matriz de columnas mediante el **Constructor UniqueConstraint.** Pase el objeto **UniqueConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es **ConstraintCollection**. También puede pasar argumentos de constructor a varias sobrecargas de la **Add** método de un **ConstraintCollection** para crear un **UniqueConstraint**. Al crear un **UniqueConstraint** para una columna o columnas, puede especificar opcionalmente si la columna o columnas son una clave principal.  
  
 También puede crear una restricción única para una columna estableciendo la propiedad **Unique** de la columna en **true**. Como alternativa, al establecer la propiedad **Unique** de una sola columna en **false,** se quita cualquier restricción única que pueda existir. Si se define una o varias columnas como clave principal de una tabla se creará automáticamente una restricción única para la columna o columnas especificadas. Si quita una columna de la **PrimaryKey** propiedad de un **DataTable**, el **UniqueConstraint** se quita.  
  
 En el ejemplo siguiente se crea un **UniqueConstraint** para dos columnas de un **DataTable**.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [Definición del esquema de DataTable](datatable-schema-definition.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
