---
description: 'Más información acerca de: Qué puede hacer con LINQ to SQL'
title: Qué puede hacer con LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: adf1d8dfab69db27d15634a12dbdfbfa287dbb4c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791756"
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="5d50f-103">Qué puede hacer con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5d50f-103">What You Can Do With LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5d50f-104">admite toda la funcionalidad clave que puede esperar un programador de SQL.</span><span class="sxs-lookup"><span data-stu-id="5d50f-104">supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="5d50f-105">Puede consultar, insertar, actualizar y eliminar información en las tablas.</span><span class="sxs-lookup"><span data-stu-id="5d50f-105">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="5d50f-106">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="5d50f-106">Selecting</span></span>  

 <span data-ttu-id="5d50f-107">La selección (*proyección*) se logra escribiendo simplemente una consulta LINQ en su propio lenguaje de programación y, a continuación, ejecutando esa consulta para recuperar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5d50f-107">Selecting (*projection*) is achieved by just writing a LINQ query in your own programming language, and then executing that query to retrieve the results.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5d50f-108">traduce automáticamente todas las operaciones necesarias a las operaciones SQL correspondientes con la que ya está familiarizado.</span><span class="sxs-lookup"><span data-stu-id="5d50f-108">itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="5d50f-109">Para más información, vea [LINQ to SQL](index.md).</span><span class="sxs-lookup"><span data-stu-id="5d50f-109">For more information, see [LINQ to SQL](index.md).</span></span>  
  
 <span data-ttu-id="5d50f-110">En el ejemplo siguiente se recuperan los nombres de las compañías de los clientes de Londres y se muestran en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="5d50f-110">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="5d50f-111">Inserción</span><span class="sxs-lookup"><span data-stu-id="5d50f-111">Inserting</span></span>  

 <span data-ttu-id="5d50f-112">Para realizar una operación `Insert`de SQL, basta con que agregue objetos al modelo de objetos que ha creado y llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="5d50f-112">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="5d50f-113">En el ejemplo siguiente se agrega un nuevo cliente, e información sobre el cliente, a la tabla `Customers` utilizando el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d50f-113">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="5d50f-114">Actualizando</span><span class="sxs-lookup"><span data-stu-id="5d50f-114">Updating</span></span>  

 <span data-ttu-id="5d50f-115">Para realizar una operación `Update` en una entrada de base de datos, primero recupere el elemento y modifíquelo directamente en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="5d50f-115">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="5d50f-116">Después de haber modificado el objeto, llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext> para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5d50f-116">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="5d50f-117">En el ejemplo siguiente se recuperan todos los clientes que son de Londres.</span><span class="sxs-lookup"><span data-stu-id="5d50f-117">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="5d50f-118">A continuación, el nombre de la ciudad se cambia de "London" a "London - Metro".</span><span class="sxs-lookup"><span data-stu-id="5d50f-118">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="5d50f-119">Finalmente, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5d50f-119">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="5d50f-120">Eliminando</span><span class="sxs-lookup"><span data-stu-id="5d50f-120">Deleting</span></span>  

 <span data-ttu-id="5d50f-121">Para realizar una operación `Delete` en un elemento, quite el elemento de la colección a la que pertenece y, a continuación, llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext> para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="5d50f-121">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5d50f-122">no reconoce las operaciones de eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="5d50f-122">does not recognize cascade-delete operations.</span></span> <span data-ttu-id="5d50f-123">Si desea eliminar una fila de una tabla que tiene restricciones, consulte [Cómo: eliminar filas de la base de datos](how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="5d50f-123">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="5d50f-124">En el ejemplo siguiente, se recupera el cliente cuyo `CustomerID` es `98128` de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5d50f-124">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="5d50f-125">A continuación, después de confirmar que se recuperó la fila del cliente, se llama a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> para quitar ese objeto de la colección.</span><span class="sxs-lookup"><span data-stu-id="5d50f-125">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="5d50f-126">Finalmente, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para transmitir la eliminación a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5d50f-126">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5d50f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d50f-127">See also</span></span>

- [<span data-ttu-id="5d50f-128">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="5d50f-128">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="5d50f-129">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5d50f-129">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="5d50f-130">Introducción</span><span class="sxs-lookup"><span data-stu-id="5d50f-130">Getting Started</span></span>](getting-started.md)
