---
title: Filtrar para insertar filas en la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: cb2319d51e0518114a04eea2fc7ab6b5a836b7ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328600"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="a92be-102">Filtrar para insertar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="a92be-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="a92be-103">Insertar filas en una base de datos agregando objetos al asociado [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> colección y, a continuación, enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a92be-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a92be-104">Convierte los cambios en el código SQL apropiado `INSERT` comandos.</span><span class="sxs-lookup"><span data-stu-id="a92be-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a92be-105">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="a92be-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="a92be-106">Para obtener más información, consulte [personalizar Insert, Update y las operaciones de eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a92be-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="a92be-107">Los desarrolladores que usan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="a92be-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="a92be-108">En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="a92be-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="a92be-109">Para obtener más información, vea [Cómo: Conectarse a una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="a92be-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="a92be-110">Para insertar una fila en la base de datos</span><span class="sxs-lookup"><span data-stu-id="a92be-110">To insert a row into the database</span></span>  
  
1. <span data-ttu-id="a92be-111">Cree un nuevo objeto que incluya los datos de la columna que se van a enviar.</span><span class="sxs-lookup"><span data-stu-id="a92be-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2. <span data-ttu-id="a92be-112">Agregar el nuevo objeto a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` colección asociada con la tabla de destino en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a92be-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3. <span data-ttu-id="a92be-113">Envíe el cambio a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a92be-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a92be-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a92be-114">Example</span></span>  
 <span data-ttu-id="a92be-115">En el ejemplo de código siguiente se crea un nuevo objeto de tipo `Order` y se llena con los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="a92be-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="a92be-116">Después, se agrega el nuevo objeto a la colección `Order`.</span><span class="sxs-lookup"><span data-stu-id="a92be-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="a92be-117">Finalmente, se envía el cambio a la base de datos, como una nueva fila de la tabla `Orders`.</span><span class="sxs-lookup"><span data-stu-id="a92be-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a92be-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a92be-118">See also</span></span>

- [<span data-ttu-id="a92be-119">Filtrar para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="a92be-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="a92be-120">DataContext (Métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="a92be-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="a92be-121">Filtrar Asignación de procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="a92be-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="a92be-122">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="a92be-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
