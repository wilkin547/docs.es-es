---
title: Controlar eventos de DataSet
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
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a11d80e0aee459b3bbc985f38f482d5b1db61c70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="handling-dataset-events"></a><span data-ttu-id="3639b-102">Controlar eventos de DataSet</span><span class="sxs-lookup"><span data-stu-id="3639b-102">Handling DataSet Events</span></span>
<span data-ttu-id="3639b-103">El objeto <xref:System.Data.DataSet> proporciona tres eventos: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>y <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="3639b-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="3639b-104">Evento MergeFailed</span><span class="sxs-lookup"><span data-stu-id="3639b-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="3639b-105">El evento de uso más común del objeto `DataSet` es `MergeFailed`, que se inicia cuando los esquemas de los objetos `DataSet` que se están combinando entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="3639b-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="3639b-106">Esto se produce cuando los objetos <xref:System.Data.DataRow> de origen y de destino tienen el mismo valor de clave principal y la propiedad <xref:System.Data.DataSet.EnforceConstraints%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="3639b-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="3639b-107">Por ejemplo, si las columnas de clave principal de una tabla que se está combinando son las mismas entre las tablas de los dos objetos `DataSet` , se produce una excepción y se provoca el evento `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="3639b-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="3639b-108">El objeto <xref:System.Data.MergeFailedEventArgs> pasado como parámetro al evento `MergeFailed` tiene una propiedad <xref:System.Data.MergeFailedEventArgs.Conflict%2A> que identifica el conflicto en el esquema entre los dos objetos `DataSet` , y una propiedad <xref:System.Data.MergeFailedEventArgs.Table%2A> que identifica el nombre de la tabla en conflicto.</span><span class="sxs-lookup"><span data-stu-id="3639b-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="3639b-109">En el fragmento de código siguiente se muestra cómo agregar un controlador de eventos para el evento `MergeFailed`.</span><span class="sxs-lookup"><span data-stu-id="3639b-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
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
  
## <a name="the-initialized-event"></a><span data-ttu-id="3639b-110">Evento Initialized</span><span class="sxs-lookup"><span data-stu-id="3639b-110">The Initialized Event</span></span>  
 <span data-ttu-id="3639b-111">El evento <xref:System.Data.DataSet.Initialized> se produce después de que el constructor de `DataSet` inicialice una nueva instancia del objeto `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3639b-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="3639b-112">La propiedad <xref:System.Data.DataSet.IsInitialized%2A> devuelve `true` si se ha completado la inicialización de `DataSet` ; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="3639b-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="3639b-113">El método <xref:System.Data.DataSet.BeginInit%2A> , que comienza la inicialización de `DataSet`, establece <xref:System.Data.DataSet.IsInitialized%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="3639b-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="3639b-114">El método <xref:System.Data.DataSet.EndInit%2A> , que finaliza la inicialización del objeto `DataSet`, lo establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="3639b-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="3639b-115">Estos métodos los utiliza el entorno de diseño de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] para inicializar un objeto `DataSet` que está siendo utilizado por otro componente.</span><span class="sxs-lookup"><span data-stu-id="3639b-115">These methods are used by the [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="3639b-116">No los utilizará habitualmente en el código.</span><span class="sxs-lookup"><span data-stu-id="3639b-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="3639b-117">Evento Disposed</span><span class="sxs-lookup"><span data-stu-id="3639b-117">The Disposed Event</span></span>  
 <span data-ttu-id="3639b-118">El objeto`DataSet` se deriva de la clase <xref:System.ComponentModel.MarshalByValueComponent> , que expone el método <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> y el evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> .</span><span class="sxs-lookup"><span data-stu-id="3639b-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="3639b-119">El <xref:System.ComponentModel.MarshalByValueComponent.Disposed> evento agrega un controlador de eventos para escuchar el evento disposed en el componente.</span><span class="sxs-lookup"><span data-stu-id="3639b-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="3639b-120">Puede usar el <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventos de un `DataSet` si desea ejecutar código cuando el <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="3639b-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="3639b-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>Libera los recursos utilizados por la <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="3639b-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3639b-122">El `DataSet` y `DataTable` objetos heredan de <xref:System.ComponentModel.MarshalByValueComponent> y admitir la <xref:System.Runtime.Serialization.ISerializable> interfaz para la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="3639b-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="3639b-123">Éstos son los únicos objetos ADO.NET a los que se puede tener acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="3639b-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="3639b-124">Para obtener más información, consulta [Remote Objects](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58).</span><span class="sxs-lookup"><span data-stu-id="3639b-124">For more information, see [Remote Objects](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58).</span></span>  
  
 <span data-ttu-id="3639b-125">Para obtener información sobre otros eventos disponibles al trabajar con un `DataSet`, consulte [control de eventos de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) y [control de eventos de DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="3639b-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3639b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3639b-126">See Also</span></span>  
 [<span data-ttu-id="3639b-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="3639b-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="3639b-128">Validar datos</span><span class="sxs-lookup"><span data-stu-id="3639b-128">Validating Data</span></span>](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 [<span data-ttu-id="3639b-129">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3639b-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="3639b-130">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="3639b-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
