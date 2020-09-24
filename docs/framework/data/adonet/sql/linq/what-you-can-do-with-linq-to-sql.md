---
title: Qué puede hacer con LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: a2e65cb558eec3cec21ea0efbcc66bb8c56ec7b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163926"
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="cdd84-102">Qué puede hacer con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cdd84-102">What You Can Do With LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="cdd84-103">admite toda la funcionalidad clave que puede esperar un programador de SQL.</span><span class="sxs-lookup"><span data-stu-id="cdd84-103">supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="cdd84-104">Puede consultar, insertar, actualizar y eliminar información en las tablas.</span><span class="sxs-lookup"><span data-stu-id="cdd84-104">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="cdd84-105">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="cdd84-105">Selecting</span></span>  

 <span data-ttu-id="cdd84-106">La selección (*proyección*) se logra escribiendo simplemente una consulta LINQ en su propio lenguaje de programación y, a continuación, ejecutando esa consulta para recuperar los resultados.</span><span class="sxs-lookup"><span data-stu-id="cdd84-106">Selecting (*projection*) is achieved by just writing a LINQ query in your own programming language, and then executing that query to retrieve the results.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="cdd84-107">traduce automáticamente todas las operaciones necesarias a las operaciones SQL correspondientes con la que ya está familiarizado.</span><span class="sxs-lookup"><span data-stu-id="cdd84-107">itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="cdd84-108">Para más información, vea [LINQ to SQL](index.md).</span><span class="sxs-lookup"><span data-stu-id="cdd84-108">For more information, see [LINQ to SQL](index.md).</span></span>  
  
 <span data-ttu-id="cdd84-109">En el ejemplo siguiente se recuperan los nombres de las compañías de los clientes de Londres y se muestran en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="cdd84-109">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="cdd84-110">Inserción</span><span class="sxs-lookup"><span data-stu-id="cdd84-110">Inserting</span></span>  

 <span data-ttu-id="cdd84-111">Para realizar una operación `Insert`de SQL, basta con que agregue objetos al modelo de objetos que ha creado y llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="cdd84-111">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="cdd84-112">En el ejemplo siguiente se agrega un nuevo cliente, e información sobre el cliente, a la tabla `Customers` utilizando el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="cdd84-112">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="cdd84-113">Actualizando</span><span class="sxs-lookup"><span data-stu-id="cdd84-113">Updating</span></span>  

 <span data-ttu-id="cdd84-114">Para realizar una operación `Update` en una entrada de base de datos, primero recupere el elemento y modifíquelo directamente en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="cdd84-114">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="cdd84-115">Después de haber modificado el objeto, llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext> para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cdd84-115">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="cdd84-116">En el ejemplo siguiente se recuperan todos los clientes que son de Londres.</span><span class="sxs-lookup"><span data-stu-id="cdd84-116">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="cdd84-117">A continuación, el nombre de la ciudad se cambia de "London" a "London - Metro".</span><span class="sxs-lookup"><span data-stu-id="cdd84-117">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="cdd84-118">Finalmente, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cdd84-118">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="cdd84-119">Eliminando</span><span class="sxs-lookup"><span data-stu-id="cdd84-119">Deleting</span></span>  

 <span data-ttu-id="cdd84-120">Para realizar una operación `Delete` en un elemento, quite el elemento de la colección a la que pertenece y, a continuación, llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext> para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="cdd84-120">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="cdd84-121">no reconoce las operaciones de eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="cdd84-121">does not recognize cascade-delete operations.</span></span> <span data-ttu-id="cdd84-122">Si desea eliminar una fila de una tabla que tiene restricciones, consulte [Cómo: eliminar filas de la base de datos](how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="cdd84-122">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="cdd84-123">En el ejemplo siguiente, se recupera el cliente cuyo `CustomerID` es `98128` de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cdd84-123">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="cdd84-124">A continuación, después de confirmar que se recuperó la fila del cliente, se llama a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> para quitar ese objeto de la colección.</span><span class="sxs-lookup"><span data-stu-id="cdd84-124">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="cdd84-125">Finalmente, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para transmitir la eliminación a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cdd84-125">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cdd84-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cdd84-126">See also</span></span>

- [<span data-ttu-id="cdd84-127">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="cdd84-127">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="cdd84-128">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cdd84-128">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="cdd84-129">Introducción</span><span class="sxs-lookup"><span data-stu-id="cdd84-129">Getting Started</span></span>](getting-started.md)
