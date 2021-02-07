---
description: 'Más información acerca de cómo: resolver conflictos sobrescribiendo valores de base de datos'
title: Procedimiento para resolver conflictos sobrescribiendo valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 4eaa66b4bb49706bb1ca6449d24c688a89f2750b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723509"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="7cdce-103">Procedimiento para resolver conflictos sobrescribiendo valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="7cdce-103">How to: Resolve Conflicts by Overwriting Database Values</span></span>

<span data-ttu-id="7cdce-104">Para conciliar las diferencias existentes entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> para sobrescribir los valores de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7cdce-104">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="7cdce-105">Para obtener más información, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7cdce-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cdce-106">En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="7cdce-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="7cdce-107">Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="7cdce-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cdce-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cdce-108">Example</span></span>  

 <span data-ttu-id="7cdce-109">En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.</span><span class="sxs-lookup"><span data-stu-id="7cdce-109">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="7cdce-110">En la tabla siguiente se muestra la situación.</span><span class="sxs-lookup"><span data-stu-id="7cdce-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="7cdce-111">Manager</span><span class="sxs-lookup"><span data-stu-id="7cdce-111">Manager</span></span>|<span data-ttu-id="7cdce-112">Asistente</span><span class="sxs-lookup"><span data-stu-id="7cdce-112">Assistant</span></span>|<span data-ttu-id="7cdce-113">department</span><span class="sxs-lookup"><span data-stu-id="7cdce-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="7cdce-114">Estado de la base de datos original cuando la consultan User1 y User2.</span><span class="sxs-lookup"><span data-stu-id="7cdce-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="7cdce-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="7cdce-115">Alfreds</span></span>|<span data-ttu-id="7cdce-116">Maria</span><span class="sxs-lookup"><span data-stu-id="7cdce-116">Maria</span></span>|<span data-ttu-id="7cdce-117">Sales</span><span class="sxs-lookup"><span data-stu-id="7cdce-117">Sales</span></span>|  
|<span data-ttu-id="7cdce-118">User1 se prepara para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7cdce-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="7cdce-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="7cdce-119">Alfred</span></span>||<span data-ttu-id="7cdce-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="7cdce-120">Marketing</span></span>|  
|<span data-ttu-id="7cdce-121">User2 ya ha enviado los cambios.</span><span class="sxs-lookup"><span data-stu-id="7cdce-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="7cdce-122">Mary</span><span class="sxs-lookup"><span data-stu-id="7cdce-122">Mary</span></span>|<span data-ttu-id="7cdce-123">Servicio</span><span class="sxs-lookup"><span data-stu-id="7cdce-123">Service</span></span>|  
  
 <span data-ttu-id="7cdce-124">User1 decide resolver este conflicto sobrescribiendo los valores de la base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="7cdce-124">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="7cdce-125">Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, el resultado en la base de datos es como en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cdce-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="7cdce-126">Manager</span><span class="sxs-lookup"><span data-stu-id="7cdce-126">Manager</span></span>|<span data-ttu-id="7cdce-127">Asistente</span><span class="sxs-lookup"><span data-stu-id="7cdce-127">Assistant</span></span>|<span data-ttu-id="7cdce-128">department</span><span class="sxs-lookup"><span data-stu-id="7cdce-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="7cdce-129">Nuevo estado tras la resolución del conflicto.</span><span class="sxs-lookup"><span data-stu-id="7cdce-129">New state after conflict resolution.</span></span>|<span data-ttu-id="7cdce-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="7cdce-130">Alfred</span></span><br /><br /> <span data-ttu-id="7cdce-131">(de User1)</span><span class="sxs-lookup"><span data-stu-id="7cdce-131">(from User1)</span></span>|<span data-ttu-id="7cdce-132">Maria</span><span class="sxs-lookup"><span data-stu-id="7cdce-132">Maria</span></span><br /><br /> <span data-ttu-id="7cdce-133">(original)</span><span class="sxs-lookup"><span data-stu-id="7cdce-133">(original)</span></span>|<span data-ttu-id="7cdce-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="7cdce-134">Marketing</span></span><br /><br /> <span data-ttu-id="7cdce-135">(de User1)</span><span class="sxs-lookup"><span data-stu-id="7cdce-135">(from User1)</span></span>|  
  
 <span data-ttu-id="7cdce-136">En el siguiente ejemplo de código se muestra cómo sobrescribir los valores de base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="7cdce-136">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="7cdce-137">(No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.)</span><span class="sxs-lookup"><span data-stu-id="7cdce-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7cdce-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cdce-138">See also</span></span>

- [<span data-ttu-id="7cdce-139">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="7cdce-139">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
