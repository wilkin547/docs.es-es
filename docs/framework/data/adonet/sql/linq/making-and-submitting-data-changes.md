---
description: Más información acerca de cómo realizar y enviar cambios de datos
title: Realizar y enviar cambios de datos
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 260dab911057b45250d44ded7c254dd903e2aed7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695580"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="f5bb2-103">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="f5bb2-103">Making and Submitting Data Changes</span></span>

<span data-ttu-id="f5bb2-104">En los temas de esta sección se describe cómo realizar y transmitir cambios en la base de datos y cómo administrar los conflictos de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-104">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="f5bb2-105">Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="f5bb2-106">Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f5bb2-106">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="f5bb2-107">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f5bb2-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f5bb2-108">In This Section</span></span>

<span data-ttu-id="f5bb2-109">[Cómo: Insertar filas en la base de datos](how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-109">[How to: Insert Rows Into the Database](how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="f5bb2-110">Describe cómo insertar filas en la base de datos agregando objetos al modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-110">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="f5bb2-111">[Cómo: actualizar filas en la base de datos](how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-111">[How to: Update Rows in the Database](how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="f5bb2-112">Describe cómo actualizar filas en la base de datos actualizando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-112">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="f5bb2-113">[Cómo: eliminar filas de la base de datos](how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-113">[How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="f5bb2-114">Describe cómo eliminar filas en la base de datos eliminando objetos en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-114">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="f5bb2-115">[Cómo: enviar cambios a la base de datos](how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-115">[How to: Submit Changes to the Database](how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="f5bb2-116">Describe cómo enviar los cambios del modelo de objetos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-116">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="f5bb2-117">[Cómo: corchete los envíos de datos mediante transacciones](how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-117">[How to: Bracket Data Submissions by Using Transactions](how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="f5bb2-118">Describe cómo incluir operaciones en una transacción.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-118">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="f5bb2-119">[Cómo: crear dinámicamente una base de datos](how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-119">[How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="f5bb2-120">Describe cómo generar bases de datos dinámicamente y algunos escenarios típicos de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-120">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="f5bb2-121">[Cómo: administrar conflictos de cambios](how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb2-121">[How to: Manage Change Conflicts](how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="f5bb2-122">Describe técnicas para resolver problemas de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="f5bb2-122">Describes techniques for addressing optimistic concurrency issues.</span></span>
