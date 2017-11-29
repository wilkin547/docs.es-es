---
title: "Cómo: Resolver conflictos de simultaneidad mediante combinaciones con valores de base de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8e5114052951950c5866d80c974555678b1d040a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a><span data-ttu-id="d07ba-102">Cómo: Resolver conflictos de simultaneidad mediante combinaciones con valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="d07ba-102">How to: Resolve Conflicts by Merging with Database Values</span></span>
<span data-ttu-id="d07ba-103">Para resolver las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.KeepChanges> para combinar los valores de base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="d07ba-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepChanges> to merge database values with the current client member values.</span></span> <span data-ttu-id="d07ba-104">Para obtener más información, consulte [simultaneidad optimista: información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d07ba-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d07ba-105">En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d07ba-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="d07ba-106">Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="d07ba-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d07ba-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d07ba-107">Example</span></span>  
 <span data-ttu-id="d07ba-108">En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.</span><span class="sxs-lookup"><span data-stu-id="d07ba-108">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="d07ba-109">En la tabla siguiente se muestra la situación.</span><span class="sxs-lookup"><span data-stu-id="d07ba-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="d07ba-110">Administrador</span><span class="sxs-lookup"><span data-stu-id="d07ba-110">Manager</span></span>|<span data-ttu-id="d07ba-111">Asistente</span><span class="sxs-lookup"><span data-stu-id="d07ba-111">Assistant</span></span>|<span data-ttu-id="d07ba-112">Department</span><span class="sxs-lookup"><span data-stu-id="d07ba-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="d07ba-113">Estado de la base de datos original cuando la consultan User1 y User2.</span><span class="sxs-lookup"><span data-stu-id="d07ba-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="d07ba-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="d07ba-114">Alfreds</span></span>|<span data-ttu-id="d07ba-115">Maria</span><span class="sxs-lookup"><span data-stu-id="d07ba-115">Maria</span></span>|<span data-ttu-id="d07ba-116">Ventas</span><span class="sxs-lookup"><span data-stu-id="d07ba-116">Sales</span></span>|  
|<span data-ttu-id="d07ba-117">User1 se prepara para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d07ba-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="d07ba-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="d07ba-118">Alfred</span></span>||<span data-ttu-id="d07ba-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="d07ba-119">Marketing</span></span>|  
|<span data-ttu-id="d07ba-120">User2 ya ha enviado los cambios.</span><span class="sxs-lookup"><span data-stu-id="d07ba-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="d07ba-121">Mary</span><span class="sxs-lookup"><span data-stu-id="d07ba-121">Mary</span></span>|<span data-ttu-id="d07ba-122">Servicio</span><span class="sxs-lookup"><span data-stu-id="d07ba-122">Service</span></span>|  
  
 <span data-ttu-id="d07ba-123">User1 decide resolver este conflicto combinando los valores de la base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="d07ba-123">User1 decides to resolve this conflict by merging database values with the current client member values.</span></span> <span data-ttu-id="d07ba-124">El resultado será que los valores de la base de datos se sobrescribirán cuando el conjunto de cambios actual haya modificado también ese valor.</span><span class="sxs-lookup"><span data-stu-id="d07ba-124">The result will be that database values are overwritten only when the current changeset has also modified that value.</span></span>  
  
 <span data-ttu-id="d07ba-125">Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.KeepChanges>, el resultado en la base de datos es como en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="d07ba-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepChanges>, the result in the database is as in the following table:</span></span>  
  
||<span data-ttu-id="d07ba-126">Administrador</span><span class="sxs-lookup"><span data-stu-id="d07ba-126">Manager</span></span>|<span data-ttu-id="d07ba-127">Asistente</span><span class="sxs-lookup"><span data-stu-id="d07ba-127">Assistant</span></span>|<span data-ttu-id="d07ba-128">Department</span><span class="sxs-lookup"><span data-stu-id="d07ba-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="d07ba-129">Nuevo estado tras la resolución del conflicto.</span><span class="sxs-lookup"><span data-stu-id="d07ba-129">New state after conflict resolution.</span></span>|<span data-ttu-id="d07ba-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="d07ba-130">Alfred</span></span><br /><br /> <span data-ttu-id="d07ba-131">(de User1)</span><span class="sxs-lookup"><span data-stu-id="d07ba-131">(from User1)</span></span>|<span data-ttu-id="d07ba-132">Mary</span><span class="sxs-lookup"><span data-stu-id="d07ba-132">Mary</span></span><br /><br /> <span data-ttu-id="d07ba-133">(de User2)</span><span class="sxs-lookup"><span data-stu-id="d07ba-133">(from User2)</span></span>|<span data-ttu-id="d07ba-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="d07ba-134">Marketing</span></span><br /><br /> <span data-ttu-id="d07ba-135">(de User1)</span><span class="sxs-lookup"><span data-stu-id="d07ba-135">(from User1)</span></span>|  
  
 <span data-ttu-id="d07ba-136">En el ejemplo siguiente se muestra cómo combinar los valores de la base de datos con los valores de miembro de cliente actuales (a menos que el cliente también haya cambiado ese valor).</span><span class="sxs-lookup"><span data-stu-id="d07ba-136">The following example shows how to merge database values with the current client member values (unless the client has also changed that value).</span></span> <span data-ttu-id="d07ba-137">No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="d07ba-137">No inspection or custom handling of individual member conflicts occurs.</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d07ba-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d07ba-138">See Also</span></span>  
 [<span data-ttu-id="d07ba-139">Cómo: resolver conflictos sobrescribiendo los valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d07ba-139">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 [<span data-ttu-id="d07ba-140">Cómo: resolver conflictos al conservar los valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d07ba-140">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 [<span data-ttu-id="d07ba-141">Cómo: administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="d07ba-141">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
