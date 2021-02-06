---
description: Más información acerca de cómo controlar eventos de conjunto de DataSet
title: Controlar eventos de DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: a0000396c7c1e2762a5a2937f7979d917257facc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652372"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="571b9-103">Controlar eventos de DataSet</span><span class="sxs-lookup"><span data-stu-id="571b9-103">Handling DataSet Events</span></span>

<span data-ttu-id="571b9-104">El objeto <xref:System.Data.DataSet> proporciona tres eventos: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>y <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="571b9-104">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="571b9-105">Evento MergeFailed</span><span class="sxs-lookup"><span data-stu-id="571b9-105">The MergeFailed Event</span></span>  

 <span data-ttu-id="571b9-106">El evento de uso más común del objeto `DataSet` es `MergeFailed`, que se inicia cuando los esquemas de los objetos `DataSet` que se están combinando entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="571b9-106">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="571b9-107">Esto se produce cuando los objetos <xref:System.Data.DataRow> de origen y de destino tienen el mismo valor de clave principal y la propiedad <xref:System.Data.DataSet.EnforceConstraints%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="571b9-107">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="571b9-108">Por ejemplo, si las columnas de clave principal de una tabla que se está combinando son las mismas entre las tablas de los dos objetos `DataSet` , se produce una excepción y se provoca el evento `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="571b9-108">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="571b9-109">El objeto <xref:System.Data.MergeFailedEventArgs> pasado como parámetro al evento `MergeFailed` tiene una propiedad <xref:System.Data.MergeFailedEventArgs.Conflict%2A> que identifica el conflicto en el esquema entre los dos objetos `DataSet` , y una propiedad <xref:System.Data.MergeFailedEventArgs.Table%2A> que identifica el nombre de la tabla en conflicto.</span><span class="sxs-lookup"><span data-stu-id="571b9-109">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="571b9-110">En el fragmento de código siguiente se muestra cómo agregar un controlador de eventos para el evento `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="571b9-110">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
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
  
## <a name="the-initialized-event"></a><span data-ttu-id="571b9-111">Evento Initialized</span><span class="sxs-lookup"><span data-stu-id="571b9-111">The Initialized Event</span></span>  

 <span data-ttu-id="571b9-112">El evento <xref:System.Data.DataSet.Initialized> se produce después de que el constructor de `DataSet` inicialice una nueva instancia del objeto `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="571b9-112">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="571b9-113">La propiedad <xref:System.Data.DataSet.IsInitialized%2A> devuelve `true` si se ha completado la inicialización de `DataSet` ; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="571b9-113">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="571b9-114">El método <xref:System.Data.DataSet.BeginInit%2A> , que comienza la inicialización de `DataSet`, establece <xref:System.Data.DataSet.IsInitialized%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="571b9-114">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="571b9-115">El método <xref:System.Data.DataSet.EndInit%2A> , que finaliza la inicialización del objeto `DataSet`, lo establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="571b9-115">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="571b9-116">El entorno de diseño de Visual Studio usa estos métodos para inicializar un `DataSet` que está siendo utilizado por otro componente.</span><span class="sxs-lookup"><span data-stu-id="571b9-116">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="571b9-117">No los utilizará habitualmente en el código.</span><span class="sxs-lookup"><span data-stu-id="571b9-117">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="571b9-118">Evento Disposed</span><span class="sxs-lookup"><span data-stu-id="571b9-118">The Disposed Event</span></span>  

 <span data-ttu-id="571b9-119">El objeto`DataSet` se deriva de la clase <xref:System.ComponentModel.MarshalByValueComponent> , que expone el método <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> y el evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> .</span><span class="sxs-lookup"><span data-stu-id="571b9-119">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="571b9-120">El <xref:System.ComponentModel.MarshalByValueComponent.Disposed> evento agrega un controlador de eventos para escuchar el evento eliminado en el componente.</span><span class="sxs-lookup"><span data-stu-id="571b9-120">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="571b9-121">Puede usar el <xref:System.ComponentModel.MarshalByValueComponent.Disposed> evento de un `DataSet` si desea ejecutar código cuando <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="571b9-121">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="571b9-122"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> libera los recursos utilizados por <xref:System.ComponentModel.MarshalByValueComponent> .</span><span class="sxs-lookup"><span data-stu-id="571b9-122"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="571b9-123">Los `DataSet` objetos y se `DataTable` heredan de <xref:System.ComponentModel.MarshalByValueComponent> y admiten la <xref:System.Runtime.Serialization.ISerializable> interfaz para la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="571b9-123">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="571b9-124">Éstos son los únicos objetos ADO.NET a los que se puede tener acceso remoto.</span><span class="sxs-lookup"><span data-stu-id="571b9-124">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="571b9-125">Para obtener más información, vea [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="571b9-125">For more information, see [.NET Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="571b9-126">Para obtener información sobre otros eventos disponibles al trabajar con `DataSet` , vea [controlar eventos DataTable](handling-datatable-events.md) y [controlar eventos DataAdapter](../handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="571b9-126">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](handling-datatable-events.md) and [Handling DataAdapter Events](../handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571b9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="571b9-127">See also</span></span>

- [<span data-ttu-id="571b9-128">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="571b9-128">DataSets, DataTables, and DataViews</span></span>](index.md)
- <span data-ttu-id="571b9-129">[Validar datos](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="571b9-129">[Validating Data](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span></span>
- [<span data-ttu-id="571b9-130">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="571b9-130">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="571b9-131">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="571b9-131">ADO.NET Overview</span></span>](../ado-net-overview.md)
