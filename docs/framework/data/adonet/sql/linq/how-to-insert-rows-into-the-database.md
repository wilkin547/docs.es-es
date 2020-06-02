---
title: Procedimiento para insertar filas en la base de datos
description: Aprenda a insertar filas en una base de datos agregando LINQ to SQL objetos a una colección relacionada con la tabla. LINQ to SQL traduce adiciones a comandos INSERT de SQL.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 39eee6edf59d2adb7de41efd88899050fbe69fd8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286357"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="16a04-104">Procedimiento para insertar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="16a04-104">How to: Insert Rows Into the Database</span></span>

<span data-ttu-id="16a04-105">Para insertar filas en una base de datos, se agregan objetos a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> colección asociada y, a continuación, se envían los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16a04-105">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="16a04-106">convierte los cambios en los comandos SQL adecuados `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="16a04-106">translates your changes into the appropriate SQL `INSERT` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="16a04-107">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="16a04-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="16a04-108">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="16a04-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="16a04-109">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="16a04-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="16a04-110">En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="16a04-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="16a04-111">Para obtener más información, consulte [Cómo: conectarse a una base de datos](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="16a04-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="16a04-112">Para insertar una fila en la base de datos</span><span class="sxs-lookup"><span data-stu-id="16a04-112">To insert a row into the database</span></span>

1. <span data-ttu-id="16a04-113">Cree un nuevo objeto que incluya los datos de la columna que se van a enviar.</span><span class="sxs-lookup"><span data-stu-id="16a04-113">Create a new object that includes the column data to be submitted.</span></span>

2. <span data-ttu-id="16a04-114">Agregue el nuevo objeto a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` colección asociada a la tabla de destino en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16a04-114">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>

3. <span data-ttu-id="16a04-115">Envíe el cambio a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16a04-115">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="16a04-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16a04-116">Example</span></span>

<span data-ttu-id="16a04-117">En el ejemplo de código siguiente se crea un nuevo objeto de tipo `Order` y se llena con los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="16a04-117">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="16a04-118">Después, se agrega el nuevo objeto a la colección `Order`.</span><span class="sxs-lookup"><span data-stu-id="16a04-118">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="16a04-119">Finalmente, se envía el cambio a la base de datos, como una nueva fila de la tabla `Orders`.</span><span class="sxs-lookup"><span data-stu-id="16a04-119">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="16a04-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16a04-120">See also</span></span>

- [<span data-ttu-id="16a04-121">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="16a04-121">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="16a04-122">DataContext (métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="16a04-122">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="16a04-123">Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="16a04-123">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="16a04-124">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="16a04-124">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
