---
title: Controlar eventos de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 5e1de3effcae5700aa25f5dbb84f2dec3a0b20f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195291"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="16f39-102">Controlar eventos de DataSet</span><span class="sxs-lookup"><span data-stu-id="16f39-102">Handling DataSet Events</span></span>
<span data-ttu-id="16f39-103">El objeto <xref:System.Data.DataSet> proporciona tres eventos: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>y <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="16f39-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="16f39-104">Evento MergeFailed</span><span class="sxs-lookup"><span data-stu-id="16f39-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="16f39-105">El evento de uso más común del objeto `DataSet` es `MergeFailed`, que se inicia cuando los esquemas de los objetos `DataSet` que se están combinando entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="16f39-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="16f39-106">Esto se produce cuando los objetos <xref:System.Data.DataRow> de origen y de destino tienen el mismo valor de clave principal y la propiedad <xref:System.Data.DataSet.EnforceConstraints%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="16f39-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="16f39-107">Por ejemplo, si las columnas de clave principal de una tabla que se está combinando son las mismas entre las tablas de los dos objetos `DataSet` , se produce una excepción y se provoca el evento `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="16f39-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="16f39-108">El objeto <xref:System.Data.MergeFailedEventArgs> pasado como parámetro al evento `MergeFailed` tiene una propiedad <xref:System.Data.MergeFailedEventArgs.Conflict%2A> que identifica el conflicto en el esquema entre los dos objetos `DataSet` , y una propiedad <xref:System.Data.MergeFailedEventArgs.Table%2A> que identifica el nombre de la tabla en conflicto.</span><span class="sxs-lookup"><span data-stu-id="16f39-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="16f39-109">En el fragmento de código siguiente se muestra cómo agregar un controlador de eventos para el evento `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="16f39-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
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
  
## <a name="the-initialized-event"></a><span data-ttu-id="16f39-110">Evento Initialized</span><span class="sxs-lookup"><span data-stu-id="16f39-110">The Initialized Event</span></span>  
 <span data-ttu-id="16f39-111">El evento <xref:System.Data.DataSet.Initialized> se produce después de que el constructor de `DataSet` inicialice una nueva instancia del objeto `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="16f39-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="16f39-112">La propiedad <xref:System.Data.DataSet.IsInitialized%2A> devuelve `true` si se ha completado la inicialización de `DataSet` ; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="16f39-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="16f39-113">El método <xref:System.Data.DataSet.BeginInit%2A> , que comienza la inicialización de `DataSet`, establece <xref:System.Data.DataSet.IsInitialized%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="16f39-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="16f39-114">El método <xref:System.Data.DataSet.EndInit%2A> , que finaliza la inicialización del objeto `DataSet`, lo establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="16f39-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="16f39-115">Estos métodos se usan por el entorno de diseño de Visual Studio para inicializar un `DataSet` que se utiliza otro componente.</span><span class="sxs-lookup"><span data-stu-id="16f39-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="16f39-116">No los utilizará habitualmente en el código.</span><span class="sxs-lookup"><span data-stu-id="16f39-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="16f39-117">Evento Disposed</span><span class="sxs-lookup"><span data-stu-id="16f39-117">The Disposed Event</span></span>  
 `DataSet` <span data-ttu-id="16f39-118">se deriva el <xref:System.ComponentModel.MarshalByValueComponent> (clase), que expone el <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> método y el <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventos.</span><span class="sxs-lookup"><span data-stu-id="16f39-118">is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="16f39-119">El <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventos agrega un controlador de eventos para escuchar el evento eliminado en el componente.</span><span class="sxs-lookup"><span data-stu-id="16f39-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="16f39-120">Puede usar el <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventos de un `DataSet` si desea ejecutar código cuando el <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="16f39-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> <span data-ttu-id="16f39-121">Libera los recursos utilizados por la <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="16f39-121">releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16f39-122">El `DataSet` y `DataTable` objetos heredan de <xref:System.ComponentModel.MarshalByValueComponent> y admitir la <xref:System.Runtime.Serialization.ISerializable> interfaz para la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="16f39-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="16f39-123">Éstos son los únicos objetos ADO.NET a los que se puede tener acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="16f39-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="16f39-124">Para obtener más información, consulte [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="16f39-124">For more information, see [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="16f39-125">Para obtener información sobre otros eventos disponibles al trabajar con un `DataSet`, consulte [controlar eventos de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) y [controlar eventos de DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="16f39-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f39-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="16f39-126">See also</span></span>

- [<span data-ttu-id="16f39-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="16f39-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="16f39-128">Validar datos</span><span class="sxs-lookup"><span data-stu-id="16f39-128">Validating Data</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [<span data-ttu-id="16f39-129">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="16f39-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="16f39-130">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="16f39-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
