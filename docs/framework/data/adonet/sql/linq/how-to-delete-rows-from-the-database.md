---
title: Filtrar para eliminar filas de la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 401d445e49e3712b8c59fa9bc9a2e53500a5db16
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331681"
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="ea61d-102">Filtrar para eliminar filas de la base de datos</span><span class="sxs-lookup"><span data-stu-id="ea61d-102">How to: Delete Rows From the Database</span></span>
<span data-ttu-id="ea61d-103">Puede eliminar filas en una base de datos mediante la eliminación de la correspondiente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objetos de su colección relacionada con la tabla.</span><span class="sxs-lookup"><span data-stu-id="ea61d-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea61d-104">Convierte los cambios en el código SQL apropiado `DELETE` comandos.</span><span class="sxs-lookup"><span data-stu-id="ea61d-104">translates your changes to the appropriate SQL `DELETE` commands.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea61d-105">no admite ni reconoce las operaciones de eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="ea61d-105">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="ea61d-106">Si desea eliminar una fila de una tabla que tiene restricciones, deberá realizar una de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="ea61d-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>  
  
-   <span data-ttu-id="ea61d-107">Establezca la regla `ON DELETE CASCADE` en la restricción de clave externa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ea61d-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
-   <span data-ttu-id="ea61d-108">Utilice su propio código para eliminar primero los objetos secundarios que impiden que se elimine el objeto primario.</span><span class="sxs-lookup"><span data-stu-id="ea61d-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="ea61d-109">De lo contrario, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="ea61d-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="ea61d-110">Vea el segundo ejemplo de código que se muestra más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="ea61d-110">See the second code example later in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea61d-111">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="ea61d-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="ea61d-112">Para obtener más información, consulte [personalizar Insert, Update y las operaciones de eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ea61d-112">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="ea61d-113">Los desarrolladores que usan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="ea61d-113">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="ea61d-114">En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="ea61d-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="ea61d-115">Para obtener más información, vea [Cómo: Conectarse a una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="ea61d-115">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="ea61d-116">Para eliminar una fila en la base de datos</span><span class="sxs-lookup"><span data-stu-id="ea61d-116">To delete a row in the database</span></span>  
  
1. <span data-ttu-id="ea61d-117">Consulte en la base de datos la fila que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="ea61d-117">Query the database for the row to be deleted.</span></span>  
  
2. <span data-ttu-id="ea61d-118">Llame al método <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea61d-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>  
  
3. <span data-ttu-id="ea61d-119">Envíe el cambio a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ea61d-119">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea61d-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea61d-120">Example</span></span>  
 <span data-ttu-id="ea61d-121">En este primer ejemplo de código se consultan en la base de datos los detalles del pedido #11000, se marcan dichos detalles para eliminarlos y se envían estos cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ea61d-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ea61d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea61d-122">Example</span></span>  
 <span data-ttu-id="ea61d-123">En este segundo ejemplo, el objetivo es quitar un pedido (#10250).</span><span class="sxs-lookup"><span data-stu-id="ea61d-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="ea61d-124">En primer lugar, el código examina la tabla `OrderDetails` para comprobar si el pedido que se va a quitar tiene elementos secundarios en ésta.</span><span class="sxs-lookup"><span data-stu-id="ea61d-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="ea61d-125">Si el pedido tiene elementos secundarios, se marcan primero los elementos secundarios y después el pedido para eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="ea61d-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="ea61d-126">El objeto <xref:System.Data.Linq.DataContext> coloca las eliminaciones en el orden correcto para que los comandos de eliminación enviados a la base de datos cumplan las restricciones de la misma.</span><span class="sxs-lookup"><span data-stu-id="ea61d-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ea61d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea61d-127">See also</span></span>

- [<span data-ttu-id="ea61d-128">Filtrar para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="ea61d-128">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="ea61d-129">Filtrar Asignación de procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="ea61d-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="ea61d-130">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="ea61d-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
