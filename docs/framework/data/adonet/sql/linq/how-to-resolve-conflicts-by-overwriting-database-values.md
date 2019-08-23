---
title: Procedimiento para resolver conflictos sobrescribiendo valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: f6721234d2d3920343bc72889c7683fb6ee662a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928757"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="6cc51-102">Procedimiento para resolver conflictos sobrescribiendo valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="6cc51-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="6cc51-103">Para conciliar las diferencias existentes entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> para sobrescribir los valores de base de datos.</span><span class="sxs-lookup"><span data-stu-id="6cc51-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="6cc51-104">Para obtener más información, [consulte simultaneidad optimista: Información](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)general.</span><span class="sxs-lookup"><span data-stu-id="6cc51-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cc51-105">En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="6cc51-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="6cc51-106">Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="6cc51-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cc51-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6cc51-107">Example</span></span>  
 <span data-ttu-id="6cc51-108">En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.</span><span class="sxs-lookup"><span data-stu-id="6cc51-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="6cc51-109">En la tabla siguiente se muestra la situación.</span><span class="sxs-lookup"><span data-stu-id="6cc51-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="6cc51-110">Administrador</span><span class="sxs-lookup"><span data-stu-id="6cc51-110">Manager</span></span>|<span data-ttu-id="6cc51-111">Asistente</span><span class="sxs-lookup"><span data-stu-id="6cc51-111">Assistant</span></span>|<span data-ttu-id="6cc51-112">department</span><span class="sxs-lookup"><span data-stu-id="6cc51-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="6cc51-113">Estado de la base de datos original cuando la consultan User1 y User2.</span><span class="sxs-lookup"><span data-stu-id="6cc51-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="6cc51-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="6cc51-114">Alfreds</span></span>|<span data-ttu-id="6cc51-115">Maria</span><span class="sxs-lookup"><span data-stu-id="6cc51-115">Maria</span></span>|<span data-ttu-id="6cc51-116">Ventas</span><span class="sxs-lookup"><span data-stu-id="6cc51-116">Sales</span></span>|  
|<span data-ttu-id="6cc51-117">User1 se prepara para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6cc51-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="6cc51-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="6cc51-118">Alfred</span></span>||<span data-ttu-id="6cc51-119">Marketing</span><span class="sxs-lookup"><span data-stu-id="6cc51-119">Marketing</span></span>|  
|<span data-ttu-id="6cc51-120">User2 ya ha enviado los cambios.</span><span class="sxs-lookup"><span data-stu-id="6cc51-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="6cc51-121">Mary</span><span class="sxs-lookup"><span data-stu-id="6cc51-121">Mary</span></span>|<span data-ttu-id="6cc51-122">Servicio</span><span class="sxs-lookup"><span data-stu-id="6cc51-122">Service</span></span>|  
  
 <span data-ttu-id="6cc51-123">User1 decide resolver este conflicto sobrescribiendo los valores de la base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="6cc51-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="6cc51-124">Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, el resultado en la base de datos es como en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cc51-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="6cc51-125">Administrador</span><span class="sxs-lookup"><span data-stu-id="6cc51-125">Manager</span></span>|<span data-ttu-id="6cc51-126">Asistente</span><span class="sxs-lookup"><span data-stu-id="6cc51-126">Assistant</span></span>|<span data-ttu-id="6cc51-127">department</span><span class="sxs-lookup"><span data-stu-id="6cc51-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="6cc51-128">Nuevo estado tras la resolución del conflicto.</span><span class="sxs-lookup"><span data-stu-id="6cc51-128">New state after conflict resolution.</span></span>|<span data-ttu-id="6cc51-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="6cc51-129">Alfred</span></span><br /><br /> <span data-ttu-id="6cc51-130">(de User1)</span><span class="sxs-lookup"><span data-stu-id="6cc51-130">(from User1)</span></span>|<span data-ttu-id="6cc51-131">Maria</span><span class="sxs-lookup"><span data-stu-id="6cc51-131">Maria</span></span><br /><br /> <span data-ttu-id="6cc51-132">(original)</span><span class="sxs-lookup"><span data-stu-id="6cc51-132">(original)</span></span>|<span data-ttu-id="6cc51-133">Marketing</span><span class="sxs-lookup"><span data-stu-id="6cc51-133">Marketing</span></span><br /><br /> <span data-ttu-id="6cc51-134">(de User1)</span><span class="sxs-lookup"><span data-stu-id="6cc51-134">(from User1)</span></span>|  
  
 <span data-ttu-id="6cc51-135">En el siguiente ejemplo de código se muestra cómo sobrescribir los valores de base de datos con los valores de miembro de cliente actuales.</span><span class="sxs-lookup"><span data-stu-id="6cc51-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="6cc51-136">(No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.)</span><span class="sxs-lookup"><span data-stu-id="6cc51-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6cc51-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cc51-137">See also</span></span>

- [<span data-ttu-id="6cc51-138">Procedimientos: Administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="6cc51-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
