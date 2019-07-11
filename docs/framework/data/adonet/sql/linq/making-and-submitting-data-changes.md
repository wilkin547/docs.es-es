---
title: Realizar y enviar cambios de datos
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 23dc45c990763e69b41608f6c3ec15a8db17bf23
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743011"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="aedd7-102">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="aedd7-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="aedd7-103">En los temas de esta sección se describe cómo realizar y transmitir cambios en la base de datos y cómo administrar los conflictos de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="aedd7-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aedd7-104">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="aedd7-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="aedd7-105">Para obtener más información, consulte [personalizar Insert, Update y las operaciones de eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="aedd7-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="aedd7-106">Los desarrolladores que usan Visual Studio pueden usar Object Relational Designer para desarrollar procedimientos almacenados para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="aedd7-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aedd7-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aedd7-107">In This Section</span></span>  
 [<span data-ttu-id="aedd7-108">Cómo: Insertar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="aedd7-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="aedd7-109">Describe cómo insertar filas en la base de datos agregando objetos al modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="aedd7-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="aedd7-110">Cómo: Actualizar las filas de la base de datos</span><span class="sxs-lookup"><span data-stu-id="aedd7-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="aedd7-111">Describe cómo actualizar filas en la base de datos actualizando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="aedd7-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="aedd7-112">Cómo: Eliminar filas de la base de datos</span><span class="sxs-lookup"><span data-stu-id="aedd7-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="aedd7-113">Describe cómo eliminar filas en la base de datos eliminando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="aedd7-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="aedd7-114">Cómo: Enviar cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="aedd7-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="aedd7-115">Describe cómo enviar los cambios del modelo de objetos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aedd7-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="aedd7-116">Cómo: Envíos de datos mediante el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="aedd7-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="aedd7-117">Describe cómo incluir operaciones en una transacción.</span><span class="sxs-lookup"><span data-stu-id="aedd7-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="aedd7-118">Cómo: Crear dinámicamente una base de datos</span><span class="sxs-lookup"><span data-stu-id="aedd7-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="aedd7-119">Describe cómo generar bases de datos dinámicamente y algunos escenarios típicos de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="aedd7-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="aedd7-120">Cómo: Administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="aedd7-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="aedd7-121">Describe técnicas para resolver problemas de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="aedd7-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
