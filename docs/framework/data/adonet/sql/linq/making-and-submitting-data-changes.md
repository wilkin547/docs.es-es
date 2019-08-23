---
title: Realizar y enviar cambios de datos
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: dd0a8288ca924cb17bdacdeeb94f81c3d27d3e4e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915773"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="dc804-102">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="dc804-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="dc804-103">En los temas de esta sección se describe cómo realizar y transmitir cambios en la base de datos y cómo administrar los conflictos de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="dc804-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc804-104">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="dc804-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="dc804-105">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="dc804-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="dc804-106">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="dc804-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc804-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dc804-107">In This Section</span></span>  
 [<span data-ttu-id="dc804-108">Cómo: Insertar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="dc804-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="dc804-109">Describe cómo insertar filas en la base de datos agregando objetos al modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="dc804-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="dc804-110">Cómo: Actualizar filas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="dc804-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="dc804-111">Describe cómo actualizar filas en la base de datos actualizando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="dc804-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="dc804-112">Cómo: Eliminar filas de la base de datos</span><span class="sxs-lookup"><span data-stu-id="dc804-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="dc804-113">Describe cómo eliminar filas en la base de datos eliminando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="dc804-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="dc804-114">Cómo: Enviar cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="dc804-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="dc804-115">Describe cómo enviar los cambios del modelo de objetos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dc804-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="dc804-116">Cómo: Envío de datos entre corchetes mediante transacciones</span><span class="sxs-lookup"><span data-stu-id="dc804-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="dc804-117">Describe cómo incluir operaciones en una transacción.</span><span class="sxs-lookup"><span data-stu-id="dc804-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="dc804-118">Cómo: Creación dinámica de una base de datos</span><span class="sxs-lookup"><span data-stu-id="dc804-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="dc804-119">Describe cómo generar bases de datos dinámicamente y algunos escenarios típicos de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="dc804-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="dc804-120">Procedimientos: Administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="dc804-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="dc804-121">Describe técnicas para resolver problemas de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="dc804-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
