---
title: Controlar eventos de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 8b93b0564bbd6d760193f11d23d97ccb2cb4c943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928511"
---
# <a name="handling-dataset-events"></a>Controlar eventos de DataSet
El objeto <xref:System.Data.DataSet> proporciona tres eventos: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>y <xref:System.Data.DataSet.MergeFailed>.  
  
## <a name="the-mergefailed-event"></a>Evento MergeFailed  
 El evento de uso más común del objeto `DataSet` es `MergeFailed`, que se inicia cuando los esquemas de los objetos `DataSet` que se están combinando entran en conflicto. Esto se produce cuando los objetos <xref:System.Data.DataRow> de origen y de destino tienen el mismo valor de clave principal y la propiedad <xref:System.Data.DataSet.EnforceConstraints%2A> se establece en `true`. Por ejemplo, si las columnas de clave principal de una tabla que se está combinando son las mismas entre las tablas de los dos objetos `DataSet` , se produce una excepción y se provoca el evento `MergeFailed` . El objeto <xref:System.Data.MergeFailedEventArgs> pasado como parámetro al evento `MergeFailed` tiene una propiedad <xref:System.Data.MergeFailedEventArgs.Conflict%2A> que identifica el conflicto en el esquema entre los dos objetos `DataSet` , y una propiedad <xref:System.Data.MergeFailedEventArgs.Table%2A> que identifica el nombre de la tabla en conflicto.  
  
 En el fragmento de código siguiente se muestra cómo agregar un controlador de eventos para el evento `MergeFailed` .  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a>Evento Initialized  
 El evento <xref:System.Data.DataSet.Initialized> se produce después de que el constructor de `DataSet` inicialice una nueva instancia del objeto `DataSet`.  
  
 La propiedad <xref:System.Data.DataSet.IsInitialized%2A> devuelve `true` si se ha completado la inicialización de `DataSet` ; de lo contrario, devuelve `false`. El método <xref:System.Data.DataSet.BeginInit%2A> , que comienza la inicialización de `DataSet`, establece <xref:System.Data.DataSet.IsInitialized%2A> en `false`. El método <xref:System.Data.DataSet.EndInit%2A> , que finaliza la inicialización del objeto `DataSet`, lo establece en `true`. El entorno de diseño de Visual Studio usa estos métodos para inicializar `DataSet` un que está siendo utilizado por otro componente. No los utilizará habitualmente en el código.  
  
## <a name="the-disposed-event"></a>Evento Disposed  
 El objeto`DataSet` se deriva de la clase <xref:System.ComponentModel.MarshalByValueComponent> , que expone el método <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> y el evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> . El <xref:System.ComponentModel.MarshalByValueComponent.Disposed> evento agrega un controlador de eventos para escuchar el evento eliminado en el componente. Puede usar el <xref:System.ComponentModel.MarshalByValueComponent.Disposed> evento de un `DataSet` si desea ejecutar código cuando se llama al <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> método. <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>libera los recursos utilizados por <xref:System.ComponentModel.MarshalByValueComponent>.  
  
> [!NOTE]
> Los `DataSet` objetos `DataTable` y se heredan de <xref:System.ComponentModel.MarshalByValueComponent> y <xref:System.Runtime.Serialization.ISerializable> admiten la interfaz para la comunicación remota. Éstos son los únicos objetos ADO.NET a los que se puede tener acceso remoto. Para obtener más información, vea [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).  
  
 Para obtener información sobre otros eventos disponibles al trabajar con `DataSet`, vea [controlar eventos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) y [controlar eventos DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vea también

- [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Validar datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [Recuperar y modificar datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
