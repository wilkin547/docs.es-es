---
title: Realizar y enviar cambios de datos
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 18468c9a2018a28e85d87155d98b0853854013fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792965"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="5ab81-102">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="5ab81-102">Making and Submitting Data Changes</span></span>

<span data-ttu-id="5ab81-103">En los temas de esta sección se describe cómo realizar y transmitir cambios en la base de datos y cómo administrar los conflictos de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="5ab81-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab81-104">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="5ab81-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="5ab81-105">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5ab81-105">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="5ab81-106">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="5ab81-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5ab81-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ab81-107">In This Section</span></span>

<span data-ttu-id="5ab81-108">[Cómo: Insertar filas en la base de datos](how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-108">[How to: Insert Rows Into the Database](how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="5ab81-109">Describe cómo insertar filas en la base de datos agregando objetos al modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="5ab81-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="5ab81-110">[Cómo: Actualizar filas en la base de datos](how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-110">[How to: Update Rows in the Database](how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="5ab81-111">Describe cómo actualizar filas en la base de datos actualizando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="5ab81-111">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="5ab81-112">[Procedimientos: Eliminar filas de la base de datos](how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-112">[How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="5ab81-113">Describe cómo eliminar filas en la base de datos eliminando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="5ab81-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="5ab81-114">[Procedimientos: Enviar cambios a la base de datos](how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-114">[How to: Submit Changes to the Database](how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="5ab81-115">Describe cómo enviar los cambios del modelo de objetos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5ab81-115">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="5ab81-116">[Cómo: Envío de datos entre corchetes mediante transacciones](how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-116">[How to: Bracket Data Submissions by Using Transactions](how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="5ab81-117">Describe cómo incluir operaciones en una transacción.</span><span class="sxs-lookup"><span data-stu-id="5ab81-117">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="5ab81-118">[Procedimientos: Creación dinámica de una base de datos](how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-118">[How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="5ab81-119">Describe cómo generar bases de datos dinámicamente y algunos escenarios típicos de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="5ab81-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="5ab81-120">[Procedimientos: Administrar conflictos de cambios](how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="5ab81-120">[How to: Manage Change Conflicts](how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="5ab81-121">Describe técnicas para resolver problemas de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="5ab81-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
