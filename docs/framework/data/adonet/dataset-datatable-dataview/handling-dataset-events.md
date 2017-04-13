---
title: "Controlar eventos de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Controlar eventos de DataSet
El objeto <xref:System.Data.DataSet> proporciona tres eventos: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized> y <xref:System.Data.DataSet.MergeFailed>.  
  
## Evento MergeFailed  
 El evento de uso más común del objeto `DataSet` es `MergeFailed`, que se inicia cuando los esquemas de los objetos `DataSet` que se están combinando entran en conflicto. Esto se produce cuando los objetos <xref:System.Data.DataRow> de origen y de destino tienen el mismo valor de clave principal y la propiedad <xref:System.Data.DataSet.EnforceConstraints%2A> se establece en `true`. Por ejemplo, si las columnas de clave principal de una tabla que se está combinando son las mismas entre las tablas de los dos objetos `DataSet`, se produce una excepción y se provoca el evento `MergeFailed`. El objeto <xref:System.Data.MergeFailedEventArgs> pasado como parámetro al evento `MergeFailed` tiene una propiedad <xref:System.Data.MergeFailedEventArgs.Conflict%2A> que identifica el conflicto en el esquema entre los dos objetos `DataSet`, y una propiedad <xref:System.Data.MergeFailedEventArgs.Table%2A> que identifica el nombre de la tabla en conflicto.  
  
 En el fragmento de código siguiente se muestra cómo agregar un controlador de eventos para el evento `MergeFailed`.  
  
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
  
## Evento Initialized  
 El evento <xref:System.Data.DataSet.Initialized> se produce después de que el constructor de `DataSet` inicialice una nueva instancia del objeto `DataSet`.  
  
 La propiedad <xref:System.Data.DataSet.IsInitialized%2A> devuelve `true` si se ha completado la inicialización de `DataSet`; de lo contrario, devuelve `false`. El método <xref:System.Data.DataSet.BeginInit%2A>, que comienza la inicialización de `DataSet`, establece <xref:System.Data.DataSet.IsInitialized%2A> en `false`. El método <xref:System.Data.DataSet.EndInit%2A>, que finaliza la inicialización del objeto `DataSet`, lo establece en `true`. Estos métodos los utiliza el entorno de diseño de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] para inicializar un objeto `DataSet` que está siendo utilizado por otro componente. No los utilizará habitualmente en el código.  
  
## Evento Disposed  
 El objeto `DataSet` se deriva de la clase <xref:System.ComponentModel.MarshalByValueComponent>, que expone el método <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> y el evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed>. El evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> agrega un controlador de eventos para escuchar el evento eliminado en el componente. Puede usar el evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> de un objeto `DataSet` si quiere ejecutar el código al llamar al método <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>.<xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> libera los recursos que usa <xref:System.ComponentModel.MarshalByValueComponent>.  
  
> [!NOTE]
>  Los objetos `DataSet` y `DataTable` se heredan de <xref:System.ComponentModel.MarshalByValueComponent> y admiten la interfaz <xref:System.Runtime.Serialization.ISerializable> para obtener acceso a ellos de forma remota. Éstos son los únicos objetos ADO.NET a los que se puede tener acceso remoto. Para obtener más información, consulta [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58).  
  
 Para obtener información sobre otros eventos disponibles al trabajar con un objeto `DataSet`, consulte [Control de eventos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) y [Control de eventos DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## Vea también  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Validar datos](../Topic/Validating%20Data.md)   
 [Recuperación y modificación de datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)