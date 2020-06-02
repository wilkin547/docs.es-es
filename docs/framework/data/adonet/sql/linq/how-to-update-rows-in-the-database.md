---
title: Procedimiento para actualizar filas en la base de datos
description: Aprenda a actualizar filas en una base de datos modificando LINQ to SQL objetos en una colección relacionada con la tabla. LINQ to SQL traduce las adiciones a los comandos de actualización de SQL.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: f25efb91fb5a83fb1c7c109bd018c8210edaec8b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286344"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="4870a-104">Procedimiento para actualizar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="4870a-104">How to: Update Rows in the Database</span></span>

<span data-ttu-id="4870a-105">Puede actualizar las filas de una base de datos modificando los valores de miembro de los objetos asociados a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> colección y, a continuación, enviando los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4870a-105">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4870a-106">convierte los cambios en los comandos SQL adecuados `UPDATE` .</span><span class="sxs-lookup"><span data-stu-id="4870a-106">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="4870a-107">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="4870a-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="4870a-108">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4870a-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="4870a-109">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="4870a-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="4870a-110">En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="4870a-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="4870a-111">Para obtener más información, consulte [Cómo: conectarse a una base de datos](how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="4870a-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="4870a-112">Para actualizar una fila de la base de datos</span><span class="sxs-lookup"><span data-stu-id="4870a-112">To update a row in the database</span></span>

1. <span data-ttu-id="4870a-113">Consulte en la base de datos la fila que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="4870a-113">Query the database for the row to be updated.</span></span>

2. <span data-ttu-id="4870a-114">Realice los cambios deseados en los valores de miembro en el objeto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] resultante.</span><span class="sxs-lookup"><span data-stu-id="4870a-114">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>

3. <span data-ttu-id="4870a-115">Envíe los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4870a-115">Submit the changes to the database.</span></span>

## <a name="example"></a><span data-ttu-id="4870a-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4870a-116">Example</span></span>

<span data-ttu-id="4870a-117">En el ejemplo siguiente se consulta en la base de datos el pedido #11000 y, a continuación, se cambian los valores de `ShipName` y `ShipVia` en el objeto `Order` resultante.</span><span class="sxs-lookup"><span data-stu-id="4870a-117">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="4870a-118">Finalmente, los cambios en estos valores de miembro se envían a la base de datos como cambios en las columnas `ShipName` y `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="4870a-118">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="4870a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4870a-119">See also</span></span>

- [<span data-ttu-id="4870a-120">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="4870a-120">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="4870a-121">Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="4870a-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="4870a-122">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="4870a-122">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
