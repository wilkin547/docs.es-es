---
title: Procedimiento para insertar filas en la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 8186b90a666a7b75ce626cccb7cc28af38de7c5b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781863"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="f0a5d-102">Procedimiento para insertar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="f0a5d-102">How to: Insert Rows Into the Database</span></span>

<span data-ttu-id="f0a5d-103">Para insertar filas en una base de datos, se agregan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objetos a la colección asociada <xref:System.Data.Linq.Table%601> y, a continuación, se envían los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="f0a5d-104">convierte los cambios en los comandos SQL `INSERT` adecuados.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a5d-105">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="f0a5d-106">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f0a5d-106">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="f0a5d-107">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="f0a5d-108">En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="f0a5d-109">Para obtener más información, vea [Cómo: Conectarse a una base](how-to-connect-to-a-database.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-109">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="f0a5d-110">Para insertar una fila en la base de datos</span><span class="sxs-lookup"><span data-stu-id="f0a5d-110">To insert a row into the database</span></span>

1. <span data-ttu-id="f0a5d-111">Cree un nuevo objeto que incluya los datos de la columna que se van a enviar.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-111">Create a new object that includes the column data to be submitted.</span></span>

2. <span data-ttu-id="f0a5d-112">Agregue el nuevo objeto a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` colección asociada a la tabla de destino en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>

3. <span data-ttu-id="f0a5d-113">Envíe el cambio a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-113">Submit the change to the database.</span></span>

## <a name="example"></a><span data-ttu-id="f0a5d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0a5d-114">Example</span></span>

<span data-ttu-id="f0a5d-115">En el ejemplo de código siguiente se crea un nuevo objeto de tipo `Order` y se llena con los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="f0a5d-116">Después, se agrega el nuevo objeto a la colección `Order`.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="f0a5d-117">Finalmente, se envía el cambio a la base de datos, como una nueva fila de la tabla `Orders`.</span><span class="sxs-lookup"><span data-stu-id="f0a5d-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="f0a5d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0a5d-118">See also</span></span>

- [<span data-ttu-id="f0a5d-119">Cómo: Administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="f0a5d-119">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="f0a5d-120">Métodos DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="f0a5d-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="f0a5d-121">Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="f0a5d-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="f0a5d-122">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="f0a5d-122">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
