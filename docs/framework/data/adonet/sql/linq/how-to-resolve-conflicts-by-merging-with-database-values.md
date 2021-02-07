---
description: 'Más información acerca de cómo: resolver conflictos mediante la combinación con valores de base de datos'
title: Procedimiento para resolver conflictos mediante combinaciones con valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: 83cae4c98fdd2e51065c66d36ef04202bdc86c9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767770"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="04415-103">Procedimiento para resolver conflictos mediante combinaciones con valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="04415-103">How to: Resolve Conflicts by Merging with Database Values</span></span>

<span data-ttu-id="04415-104">Para conciliar las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.KeepChanges> para combinar los valores de base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="04415-104">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="04415-105">Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="04415-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04415-106">En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="04415-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="04415-107">Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="04415-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04415-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04415-108">Example</span></span>  

 <span data-ttu-id="04415-109">En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.</span><span class="sxs-lookup"><span data-stu-id="04415-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="04415-110">En la tabla siguiente se muestra la situación.</span><span class="sxs-lookup"><span data-stu-id="04415-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="04415-111">Manager</span><span class="sxs-lookup"><span data-stu-id="04415-111">Manager</span></span>|<span data-ttu-id="04415-112">Asistente</span><span class="sxs-lookup"><span data-stu-id="04415-112">Assistant</span></span>|<span data-ttu-id="04415-113">department</span><span class="sxs-lookup"><span data-stu-id="04415-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="04415-114">Estado de la base de datos original cuando la consultan User1 y User2.</span><span class="sxs-lookup"><span data-stu-id="04415-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="04415-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="04415-115">Alfreds</span></span>|<span data-ttu-id="04415-116">Maria</span><span class="sxs-lookup"><span data-stu-id="04415-116">Maria</span></span>|<span data-ttu-id="04415-117">Sales</span><span class="sxs-lookup"><span data-stu-id="04415-117">Sales</span></span>|  
|<span data-ttu-id="04415-118">User1 se prepara para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="04415-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="04415-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="04415-119">Alfred</span></span>||<span data-ttu-id="04415-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="04415-120">Marketing</span></span>|  
|<span data-ttu-id="04415-121">User2 ya ha enviado los cambios.</span><span class="sxs-lookup"><span data-stu-id="04415-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="04415-122">Mary</span><span class="sxs-lookup"><span data-stu-id="04415-122">Mary</span></span>|<span data-ttu-id="04415-123">Servicio</span><span class="sxs-lookup"><span data-stu-id="04415-123">Service</span></span>|  
  
 <span data-ttu-id="04415-124">User1 decide resolver este conflicto combinando los valores de la base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="04415-124">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="04415-125">El resultado será que los valores de la base de datos se sobrescribirán cuando el conjunto de cambios actual haya modificado también ese valor.</span><span class="sxs-lookup"><span data-stu-id="04415-125">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="04415-126">Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.KeepChanges>, el resultado en la base de datos es como en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="04415-126">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="04415-127">Manager</span><span class="sxs-lookup"><span data-stu-id="04415-127">Manager</span></span>|<span data-ttu-id="04415-128">Asistente</span><span class="sxs-lookup"><span data-stu-id="04415-128">Assistant</span></span>|<span data-ttu-id="04415-129">department</span><span class="sxs-lookup"><span data-stu-id="04415-129">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="04415-130">Nuevo estado tras la resolución del conflicto.</span><span class="sxs-lookup"><span data-stu-id="04415-130">New state after conflict resolution.</span></span>|<span data-ttu-id="04415-131">Alfred</span><span class="sxs-lookup"><span data-stu-id="04415-131">Alfred</span></span><br /><br /> <span data-ttu-id="04415-132">(de User1)</span><span class="sxs-lookup"><span data-stu-id="04415-132">(from User1)</span></span>|<span data-ttu-id="04415-133">Mary</span><span class="sxs-lookup"><span data-stu-id="04415-133">Mary</span></span><br /><br /> <span data-ttu-id="04415-134">(de User2)</span><span class="sxs-lookup"><span data-stu-id="04415-134">(from User2)</span></span>|<span data-ttu-id="04415-135">Marketing</span><span class="sxs-lookup"><span data-stu-id="04415-135">Marketing</span></span><br /><br /> <span data-ttu-id="04415-136">(de User1)</span><span class="sxs-lookup"><span data-stu-id="04415-136">(from User1)</span></span>|  
  
 <span data-ttu-id="04415-137">En el ejemplo siguiente se muestra cómo combinar los valores de la base de datos con los valores de miembro de cliente actuales (a menos que el cliente también haya cambiado ese valor).</span><span class="sxs-lookup"><span data-stu-id="04415-137">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="04415-138">No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="04415-138">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="04415-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="04415-139">See also</span></span>

- [<span data-ttu-id="04415-140">Procedimiento para resolver conflictos sobrescribiendo valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="04415-140">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)
- [<span data-ttu-id="04415-141">Procedimiento para resolver conflictos conservando valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="04415-141">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)
- [<span data-ttu-id="04415-142">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="04415-142">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
