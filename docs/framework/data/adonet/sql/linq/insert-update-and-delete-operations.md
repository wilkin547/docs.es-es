---
description: Más información acerca de las operaciones de inserción, actualización y eliminación
title: Operaciones de actualización, inserción y eliminación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 2d0470ed6abe654ca08f954c3de97de207adb75d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803824"
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="5aa2f-103">Operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="5aa2f-103">Insert, Update, and Delete Operations</span></span>

<span data-ttu-id="5aa2f-104">En `Insert`, las operaciones `Update`, `Delete` y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se realizan agregando, cambiando y quitando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-104">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="5aa2f-105">De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte estas acciones a SQL y envía los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-105">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5aa2f-106">ofrece la máxima flexibilidad para manipular y conservar los cambios realizados en los objetos.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-106">offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="5aa2f-107">En cuanto están disponibles los objetos entidad (ya sea recuperándolos a través de una consulta o construyéndolos nuevamente), puede cambiarlos como los objetos normales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-107">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="5aa2f-108">Es decir, puede cambiar sus valores, agregarlos a las colecciones y quitarlos de las mismas.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-108">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5aa2f-109">realiza un seguimiento de los cambios y está listo para volver a transmitirlos a la base de datos cuando llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-109">tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5aa2f-110">no admite ni reconoce las operaciones de eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-110">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="5aa2f-111">Si desea eliminar una fila de una tabla que tiene restricciones, debe establecer la `ON DELETE CASCADE` regla en la restricción FOREIGN KEY en la base de datos, o bien usar su propio código para eliminar primero los objetos secundarios que impiden que se elimine el objeto primario.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-111">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="5aa2f-112">De lo contrario, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-112">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="5aa2f-113">Para obtener más información, consulte [Cómo: eliminar filas de la base de datos](how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="5aa2f-113">For more information, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>

<span data-ttu-id="5aa2f-114">En los siguientes extractos se utilizan las clases `Customer` y `Order` de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-114">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="5aa2f-115">Para no extendernos demasiado, no incluimos las definiciones de clase.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-115">Class definitions are not shown for brevity.</span></span>

[!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
[!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]

<span data-ttu-id="5aa2f-116">Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera y ejecuta automáticamente los comandos SQL necesarios para volver a transmitir los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-116">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>

> [!NOTE]
> <span data-ttu-id="5aa2f-117">Puede invalidar este comportamiento utilizando su propia lógica personalizada, normalmente mediante un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-117">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="5aa2f-118">Para obtener más información, consulte [responsabilidades del Desarrollador en invalidar el comportamiento predeterminado](responsibilities-of-the-developer-in-overriding-default-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="5aa2f-118">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>
>
> <span data-ttu-id="5aa2f-119">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con este fin.</span><span class="sxs-lookup"><span data-stu-id="5aa2f-119">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for this purpose.</span></span>

## <a name="see-also"></a><span data-ttu-id="5aa2f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aa2f-120">See also</span></span>

- [<span data-ttu-id="5aa2f-121">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5aa2f-121">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="5aa2f-122">Personalizar operaciones de actualización, inserción y eliminación</span><span class="sxs-lookup"><span data-stu-id="5aa2f-122">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
