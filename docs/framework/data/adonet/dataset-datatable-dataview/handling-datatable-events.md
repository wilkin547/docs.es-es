---
description: Más información sobre cómo controlar los eventos de DataTable
title: Controlar eventos de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62f404a5-13ea-4b93-a29f-55b74a16c9d3
ms.openlocfilehash: 89519345ec0c9f2348153c480366396a66d37ae0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652359"
---
# <a name="handling-datatable-events"></a>Controlar eventos de DataTable

El objeto <xref:System.Data.DataTable> proporciona una serie de eventos que una aplicación puede procesar. En la siguiente tabla se describen los eventos de `DataTable`.  
  
|Evento|Descripción|  
|-----------|-----------------|  
|<xref:System.Data.DataTable.Initialized>|Se produce después de haber llamado al método <xref:System.Data.DataTable.EndInit%2A> de un objeto `DataTable`. Este evento está concebido principalmente para admitir escenarios en tiempo de diseño.|  
|<xref:System.Data.DataTable.ColumnChanged>|Se produce después de cambiar correctamente un valor en un objeto <xref:System.Data.DataColumn>.|  
|<xref:System.Data.DataTable.ColumnChanging>|Se produce cuando se ha enviado un valor para un objeto `DataColumn`.|  
|<xref:System.Data.DataTable.RowChanged>|Se produce cuando se ha cambiado correctamente un valor de `DataColumn` o la propiedad <xref:System.Data.DataRow.RowState%2A> de un objeto <xref:System.Data.DataRow> en el objeto `DataTable`.|  
|<xref:System.Data.DataTable.RowChanging>|Se produce cuando se ha enviado un cambio para un valor `DataColumn` o la propiedad `RowState` de un objeto `DataRow` en el objeto `DataTable`.|  
|<xref:System.Data.DataTable.RowDeleted>|Se produce después de marcar un objeto `DataRow` de un objeto `DataTable` como `Deleted`.|  
|<xref:System.Data.DataTable.RowDeleting>|Se produce antes de marcar un objeto `DataRow` de un objeto `DataTable` como `Deleted`.|  
|<xref:System.Data.DataTable.TableCleared>|Se produce después de que una llamada al método <xref:System.Data.DataTable.Clear%2A> del objeto `DataTable` haya borrado correctamente todos los objetos `DataRow`.|  
|<xref:System.Data.DataTable.TableClearing>|Se produce después de haber llamado al método `Clear` pero antes de que se inicie la operación `Clear`.|  
|<xref:System.Data.DataTable.TableNewRow>|Se produce después de crear un nuevo objeto `DataRow` mediante una llamada al método `NewRow` del objeto `DataTable`.|  
|<xref:System.ComponentModel.MarshalByValueComponent.Disposed>|Se produce cuando el objeto `DataTable` se establece en `Disposed`. Se hereda de <xref:System.ComponentModel.MarshalByValueComponent>.|  
  
> [!NOTE]
> La mayoría de las operaciones que agregan o eliminan filas no generan eventos `ColumnChanged` ni `ColumnChanging`. Sin embargo, el método `ReadXml` sí genera eventos `ColumnChanged` y `ColumnChanging`, a menos que `XmlReadMode` se establezca en `DiffGram` o se establezca en `Auto` cuando el documento XML que se lee es `DiffGram`.  
  
> [!WARNING]
> Es posible que los datos resulten dañados si se modifican en un `DataSet` desde el que se genera el evento `RowChanged`. No se producirá ninguna excepción si se produce este tipo de daño en los datos.  
  
## <a name="additional-related-events"></a>Eventos relacionados adicionales  

 La propiedad <xref:System.Data.DataTable.Constraints%2A> contiene una instancia de <xref:System.Data.ConstraintCollection>. La clase <xref:System.Data.ConstraintCollection> expone un evento <xref:System.Data.ConstraintCollection.CollectionChanged>. Este evento se activa cuando se agrega, modifica o quita una restricción de `ConstraintCollection`.  
  
 La propiedad <xref:System.Data.DataTable.Columns%2A> contiene una instancia de <xref:System.Data.DataColumnCollection>. La clase `DataColumnCollection` expone un evento <xref:System.Data.DataColumnCollection.CollectionChanged>. Este evento se activa cuando se agrega, modifica o quita un objeto `DataColumn` de `DataColumnCollection`. Entre las modificaciones que generan el inicio del evento se encuentran los cambios en el nombre, el tipo, la expresión o la posición ordinal de una columna.  
  
 La propiedad <xref:System.Data.DataSet.Tables%2A> de un objeto <xref:System.Data.DataSet> incluye una instancia de <xref:System.Data.DataTableCollection>. La clase `DataTableCollection` expone los eventos `CollectionChanged` y `CollectionChanging`. Estos eventos se activan cuando se agrega o se quita un objeto `DataTable` del `DataSet`.  
  
 Los cambios en `DataRows` también pueden activar eventos de un objeto <xref:System.Data.DataView> asociado. La clase `DataView` expone un evento <xref:System.Data.DataView.ListChanged> que se activa cuando cambia un valor de `DataColumn` o cuando cambian la composición o el criterio de ordenación de la vista. La clase <xref:System.Data.DataRowView> expone un evento <xref:System.Data.DataRowView.PropertyChanged> que se activa cuando cambia un valor de `DataColumn` asociado.  
  
## <a name="sequence-of-operations"></a>Secuencia de operaciones  

 A continuación se indica la secuencia de las operaciones que tienen lugar cuando se agrega, modifica o elimina un objeto `DataRow`.  
  
1. Se crea el registro propuesto y se aplican los cambios.  
  
2. Se comprueban las restricciones en columnas que no son de expresión.  
  
3. Se generan los eventos `RowChanging` o `RowDeleting`, según corresponda.  
  
4. El registro propuesto se establece en el registro actual.  
  
5. Se actualizan los índices asociados.  
  
6. Se generan los eventos `ListChanged` de los objetos `DataView` asociados y los eventos `PropertyChanged` de los objetos `DataRowView` asociados.  
  
7. Se evalúan todas las columnas de expresión, pero se retrasa la comprobación de las restricciones de estas columnas.  
  
8. Se generan los eventos `ListChanged` de los objetos `DataView` asociados y los eventos `PropertyChanged` de los objetos `DataRowView` asociados a los que afecten las evaluaciones de la columna de expresión.  
  
9. Se generan los eventos `RowChanged` o `RowDeleted`, según corresponda.  
  
10. Se comprueban las restricciones en las columnas de expresión.  
  
> [!NOTE]
> Los cambios en las columnas de expresión nunca generan eventos `DataTable`. Los cambios en las columnas de expresión solo generan eventos `DataView` y `DataRowView`. Las columnas de expresión pueden tener dependencias en otras columnas y se pueden evaluar varias veces durante una única operación de `DataRow`. Cada evaluación de expresión genera eventos, y una sola operación de `DataRow` puede generar varios eventos `ListChanged` y `PropertyChanged` cuando se ven afectadas columnas de expresión, que posiblemente incluyen varios eventos para la misma columna de expresión.  
  
> [!WARNING]
> No inicie una excepción <xref:System.NullReferenceException> dentro del controlador de eventos `RowChanged`. Si se inicia una excepción <xref:System.NullReferenceException> dentro del evento `RowChanged` de un objeto `DataTable`, el objeto `DataTable` resultará dañado.  
  
### <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo crear controladores de eventos para los eventos `RowChanged`, `RowChanging`, `RowDeleted`, `RowDeleting`, `ColumnChanged`, `ColumnChanging`, `TableNewRow`, `TableCleared` y `TableClearing`. Cada controlador de eventos muestra resultado en la ventana de la consola cuando se activa.  
  
 [!code-csharp[DataWorks DataTable.Events#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.Events/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.Events#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.Events/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Controlar eventos de DataAdapter](../handling-dataadapter-events.md)
- [Controlar eventos de DataSet](handling-dataset-events.md)
- [Información general de ADO.NET](../ado-net-overview.md)
