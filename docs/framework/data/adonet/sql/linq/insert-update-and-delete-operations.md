---
title: "Operaciones de actualización, inserción y eliminación"
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
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: adbe7faa50b06c330b942b451d5a4a0bd832cde3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="3c5f9-102">Operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="3c5f9-102">Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="3c5f9-103">En `Insert`, las operaciones `Update`, `Delete` y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se realizan agregando, cambiando y quitando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="3c5f9-104">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte estas acciones a SQL y envía los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="3c5f9-105">proporciona la máxima flexibilidad para manipular y conservar los cambios realizados en los objetos.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-105"> offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="3c5f9-106">En cuanto están disponibles los objetos entidad (ya sea recuperándolos a través de una consulta o construyéndolos nuevamente), puede cambiarlos como los objetos normales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="3c5f9-107">Es decir, puede cambiar sus valores, puede agregarlos a las colecciones, y puede quitarlos de las colecciones.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="3c5f9-108"> realiza un seguimiento de los cambios y está listo para volver a transmitirlos a la base de datos cuando llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-108"> tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="3c5f9-109"> no admite ni reconoce las operaciones de eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-109"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="3c5f9-110">Si desea eliminar una fila de una tabla que tiene restricciones, deberá establecer el `ON DELETE CASCADE` de regla en la restricción de clave externa de la base de datos o utilizar su propio código para eliminar primero los objetos secundarios que impiden que el objeto primario que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="3c5f9-111">De lo contrario, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="3c5f9-112">Para obtener más información, consulte [Cómo: eliminar filas de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="3c5f9-112">For more information, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="3c5f9-113">En los siguientes extractos se utilizan las clases `Customer` y `Order` de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="3c5f9-114">Para no extendernos demasiado, no incluimos las definiciones de clase.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-114">Class definitions are not shown for brevity.</span></span>  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <span data-ttu-id="3c5f9-115">Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera y ejecuta automáticamente los comandos SQL necesarios para volver a transmitir los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c5f9-116">Puede invalidar este comportamiento utilizando su propia lógica personalizada, normalmente mediante un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="3c5f9-117">Para obtener más información, consulte [las responsabilidades de los desarrolladores invalidar un comportamiento predeterminado](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="3c5f9-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>  
>   
>  <span data-ttu-id="3c5f9-118">Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados con este propósito.</span><span class="sxs-lookup"><span data-stu-id="3c5f9-118">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for this purpose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5f9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c5f9-119">See Also</span></span>  
 [<span data-ttu-id="3c5f9-120">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c5f9-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="3c5f9-121">Personalizar Insertar, actualizar y eliminar operaciones</span><span class="sxs-lookup"><span data-stu-id="3c5f9-121">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
