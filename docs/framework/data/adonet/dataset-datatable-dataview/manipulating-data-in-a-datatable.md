---
title: Manipular datos en un objeto DataTable
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: f21ac216ed69db99001e324eb34cacf1254fcf6e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="0df09-102">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="0df09-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="0df09-103">Después de crear una <xref:System.Data.DataTable> en un <xref:System.Data.DataSet>, se pueden realizar las mismas actividades que al utilizar una tabla de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="0df09-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="0df09-104">Se puede agregar, ver, modificar y eliminar datos en la tabla, supervisar los errores y eventos y consultar los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="0df09-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="0df09-105">Al modificar datos en un **DataTable**, también puede comprobar si los cambios son precisos y determinan si se deben aceptar o rechazar los cambios mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0df09-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0df09-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0df09-106">In This Section</span></span>  
 [<span data-ttu-id="0df09-107">Adición de datos a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="0df09-107">Adding Data to a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-data-to-a-datatable.md)  
 <span data-ttu-id="0df09-108">Explica cómo crear nuevas filas y agregarlas a una tabla.</span><span class="sxs-lookup"><span data-stu-id="0df09-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="0df09-109">Visualización de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="0df09-109">Viewing Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/viewing-data-in-a-datatable.md)  
 <span data-ttu-id="0df09-110">Describe cómo obtener acceso a los datos de una fila, tanto en las versiones originales como en las actuales de los datos.</span><span class="sxs-lookup"><span data-stu-id="0df09-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="0df09-111">Método de carga</span><span class="sxs-lookup"><span data-stu-id="0df09-111">The Load Method</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/the-load-method.md)  
 <span data-ttu-id="0df09-112">Describe el uso de la **carga** método para rellenar un **DataTable** con filas.</span><span class="sxs-lookup"><span data-stu-id="0df09-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="0df09-113">Ediciones de DataTable</span><span class="sxs-lookup"><span data-stu-id="0df09-113">DataTable Edits</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-edits.md)  
 <span data-ttu-id="0df09-114">Explica cómo modificar los datos de una fila, incluida la suspensión de los cambios de una fila hasta que los cambios propuestos se comprueben y acepten.</span><span class="sxs-lookup"><span data-stu-id="0df09-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="0df09-115">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="0df09-115">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 <span data-ttu-id="0df09-116">Proporciona información sobre los distintos estados de una fila.</span><span class="sxs-lookup"><span data-stu-id="0df09-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="0df09-117">Eliminación de DataRow</span><span class="sxs-lookup"><span data-stu-id="0df09-117">DataRow Deletion</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarow-deletion.md)  
 <span data-ttu-id="0df09-118">Describe cómo quitar una fila de una tabla.</span><span class="sxs-lookup"><span data-stu-id="0df09-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="0df09-119">Información de error de fila</span><span class="sxs-lookup"><span data-stu-id="0df09-119">Row Error Information</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 <span data-ttu-id="0df09-120">Explica cómo insertar información de error en cada fila para solucionar problemas con los datos dentro de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="0df09-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="0df09-121">AcceptChange y RejectChange</span><span class="sxs-lookup"><span data-stu-id="0df09-121">AcceptChanges and RejectChanges</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="0df09-122">Explica cómo aceptar o rechazar los cambios realizados en una fila.</span><span class="sxs-lookup"><span data-stu-id="0df09-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df09-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0df09-123">See Also</span></span>  
 [<span data-ttu-id="0df09-124">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="0df09-124">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="0df09-125">Control de eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="0df09-125">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="0df09-126">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0df09-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
