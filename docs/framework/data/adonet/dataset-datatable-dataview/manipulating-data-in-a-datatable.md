---
description: Más información sobre cómo manipular datos en un objeto DataTable
title: Manipular datos en un objeto DataTable
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: 41f70bd15a023f8d92733bdce142666a08245d9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652073"
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="6b54d-103">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="6b54d-103">Manipulating Data in a DataTable</span></span>

<span data-ttu-id="6b54d-104">Después de crear una <xref:System.Data.DataTable> en un <xref:System.Data.DataSet>, se pueden realizar las mismas actividades que al utilizar una tabla de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6b54d-104">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="6b54d-105">Se puede agregar, ver, modificar y eliminar datos en la tabla, supervisar los errores y eventos y consultar los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6b54d-105">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="6b54d-106">Al modificar los datos de un **objeto DataTable**, también puede comprobar si los cambios son precisos y determinar si aceptar o rechazar los cambios mediante programación.</span><span class="sxs-lookup"><span data-stu-id="6b54d-106">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b54d-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6b54d-107">In This Section</span></span>  

 [<span data-ttu-id="6b54d-108">Agregar datos a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="6b54d-108">Adding Data to a DataTable</span></span>](adding-data-to-a-datatable.md)  
 <span data-ttu-id="6b54d-109">Explica cómo crear nuevas filas y agregarlas a una tabla.</span><span class="sxs-lookup"><span data-stu-id="6b54d-109">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="6b54d-110">Ver datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="6b54d-110">Viewing Data in a DataTable</span></span>](viewing-data-in-a-datatable.md)  
 <span data-ttu-id="6b54d-111">Describe cómo obtener acceso a los datos de una fila, tanto en las versiones originales como en las actuales de los datos.</span><span class="sxs-lookup"><span data-stu-id="6b54d-111">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="6b54d-112">El método de carga</span><span class="sxs-lookup"><span data-stu-id="6b54d-112">The Load Method</span></span>](the-load-method.md)  
 <span data-ttu-id="6b54d-113">Describe el uso del método **Load** para rellenar un **DataTable** con filas.</span><span class="sxs-lookup"><span data-stu-id="6b54d-113">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="6b54d-114">Ediciones de DataTable</span><span class="sxs-lookup"><span data-stu-id="6b54d-114">DataTable Edits</span></span>](datatable-edits.md)  
 <span data-ttu-id="6b54d-115">Explica cómo modificar los datos de una fila, incluida la suspensión de los cambios de una fila hasta que los cambios propuestos se comprueben y acepten.</span><span class="sxs-lookup"><span data-stu-id="6b54d-115">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="6b54d-116">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="6b54d-116">Row States and Row Versions</span></span>](row-states-and-row-versions.md)  
 <span data-ttu-id="6b54d-117">Proporciona información sobre los distintos estados de una fila.</span><span class="sxs-lookup"><span data-stu-id="6b54d-117">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="6b54d-118">Eliminación de DataRow</span><span class="sxs-lookup"><span data-stu-id="6b54d-118">DataRow Deletion</span></span>](datarow-deletion.md)  
 <span data-ttu-id="6b54d-119">Describe cómo quitar una fila de una tabla.</span><span class="sxs-lookup"><span data-stu-id="6b54d-119">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="6b54d-120">Información de error de fila</span><span class="sxs-lookup"><span data-stu-id="6b54d-120">Row Error Information</span></span>](row-error-information.md)  
 <span data-ttu-id="6b54d-121">Explica cómo insertar información de error en cada fila para solucionar problemas con los datos dentro de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b54d-121">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="6b54d-122">Objetos AcceptChange y RejectChange</span><span class="sxs-lookup"><span data-stu-id="6b54d-122">AcceptChanges and RejectChanges</span></span>](acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="6b54d-123">Explica cómo aceptar o rechazar los cambios realizados en una fila.</span><span class="sxs-lookup"><span data-stu-id="6b54d-123">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b54d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b54d-124">See also</span></span>

- [<span data-ttu-id="6b54d-125">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="6b54d-125">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="6b54d-126">Controlar eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="6b54d-126">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="6b54d-127">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6b54d-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
