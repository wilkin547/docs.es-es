---
description: Más información sobre cómo resolver conflictos conservando los valores de la base de datos
title: Procedimiento para resolver conflictos conservando valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: ef47370768ce474ccb6d941bcec0e66807290599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723496"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="8409c-103">Procedimiento para resolver conflictos conservando valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="8409c-103">How to: Resolve Conflicts by Retaining Database Values</span></span>

<span data-ttu-id="8409c-104">Para conciliar las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> para conservar los valores que se encuentran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8409c-104">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="8409c-105">Los valores actuales del modelo de objetos se sobrescriben.</span><span class="sxs-lookup"><span data-stu-id="8409c-105">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="8409c-106">Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8409c-106">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8409c-107">En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="8409c-107">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="8409c-108">Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="8409c-108">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8409c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8409c-109">Example</span></span>  

 <span data-ttu-id="8409c-110">En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.</span><span class="sxs-lookup"><span data-stu-id="8409c-110">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="8409c-111">En la tabla siguiente se muestra la situación.</span><span class="sxs-lookup"><span data-stu-id="8409c-111">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="8409c-112">Manager</span><span class="sxs-lookup"><span data-stu-id="8409c-112">Manager</span></span>|<span data-ttu-id="8409c-113">Asistente</span><span class="sxs-lookup"><span data-stu-id="8409c-113">Assistant</span></span>|<span data-ttu-id="8409c-114">department</span><span class="sxs-lookup"><span data-stu-id="8409c-114">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="8409c-115">Estado de la base de datos original cuando la consultan User1 y User2.</span><span class="sxs-lookup"><span data-stu-id="8409c-115">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="8409c-116">Alfreds</span><span class="sxs-lookup"><span data-stu-id="8409c-116">Alfreds</span></span>|<span data-ttu-id="8409c-117">Maria</span><span class="sxs-lookup"><span data-stu-id="8409c-117">Maria</span></span>|<span data-ttu-id="8409c-118">Sales</span><span class="sxs-lookup"><span data-stu-id="8409c-118">Sales</span></span>|  
|<span data-ttu-id="8409c-119">User1 se prepara para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="8409c-119">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="8409c-120">Alfred</span><span class="sxs-lookup"><span data-stu-id="8409c-120">Alfred</span></span>||<span data-ttu-id="8409c-121">Marketing</span><span class="sxs-lookup"><span data-stu-id="8409c-121">Marketing</span></span>|  
|<span data-ttu-id="8409c-122">User2 ya ha enviado los cambios.</span><span class="sxs-lookup"><span data-stu-id="8409c-122">User2 has already submitted these changes.</span></span>||<span data-ttu-id="8409c-123">Mary</span><span class="sxs-lookup"><span data-stu-id="8409c-123">Mary</span></span>|<span data-ttu-id="8409c-124">Servicio</span><span class="sxs-lookup"><span data-stu-id="8409c-124">Service</span></span>|  
  
 <span data-ttu-id="8409c-125">User1 decide resolver este conflicto haciendo que los valores más nuevos de la base de datos sobrescriban los valores actuales del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="8409c-125">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="8409c-126">Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, el resultado en la base de datos es el de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="8409c-126">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="8409c-127">Manager</span><span class="sxs-lookup"><span data-stu-id="8409c-127">Manager</span></span>|<span data-ttu-id="8409c-128">Asistente</span><span class="sxs-lookup"><span data-stu-id="8409c-128">Assistant</span></span>|<span data-ttu-id="8409c-129">department</span><span class="sxs-lookup"><span data-stu-id="8409c-129">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="8409c-130">Nuevo estado tras la resolución del conflicto.</span><span class="sxs-lookup"><span data-stu-id="8409c-130">New state after conflict resolution.</span></span>|<span data-ttu-id="8409c-131">Alfreds</span><span class="sxs-lookup"><span data-stu-id="8409c-131">Alfreds</span></span><br /><br /> <span data-ttu-id="8409c-132">(original)</span><span class="sxs-lookup"><span data-stu-id="8409c-132">(original)</span></span>|<span data-ttu-id="8409c-133">Mary</span><span class="sxs-lookup"><span data-stu-id="8409c-133">Mary</span></span><br /><br /> <span data-ttu-id="8409c-134">(de User2)</span><span class="sxs-lookup"><span data-stu-id="8409c-134">(from User2)</span></span>|<span data-ttu-id="8409c-135">Servicio</span><span class="sxs-lookup"><span data-stu-id="8409c-135">Service</span></span><br /><br /> <span data-ttu-id="8409c-136">(de User2)</span><span class="sxs-lookup"><span data-stu-id="8409c-136">(from User2)</span></span>|  
  
 <span data-ttu-id="8409c-137">El código de ejemplo siguiente muestra cómo sobrescribir los valores actuales del modelo de objetos con los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8409c-137">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="8409c-138">(No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.)</span><span class="sxs-lookup"><span data-stu-id="8409c-138">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8409c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="8409c-139">See also</span></span>

- [<span data-ttu-id="8409c-140">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="8409c-140">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
