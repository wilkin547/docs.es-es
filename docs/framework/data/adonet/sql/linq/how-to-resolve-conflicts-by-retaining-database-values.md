---
title: Procedimiento para resolver conflictos conservando valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: e42f48a188741c3ddff44f6444fa351192c8175f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793336"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="6ae8e-102">Procedimiento para resolver conflictos conservando valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="6ae8e-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="6ae8e-103">Para conciliar las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> para conservar los valores que se encuentran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="6ae8e-104">Los valores actuales del modelo de objetos se sobrescriben.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="6ae8e-105">Para obtener más información, [consulte simultaneidad optimista: Información](optimistic-concurrency-overview.md)general.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ae8e-106">En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="6ae8e-107">Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ae8e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ae8e-108">Example</span></span>  
 <span data-ttu-id="6ae8e-109">En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="6ae8e-110">En la tabla siguiente se muestra la situación.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="6ae8e-111">Administrador</span><span class="sxs-lookup"><span data-stu-id="6ae8e-111">Manager</span></span>|<span data-ttu-id="6ae8e-112">Asistente</span><span class="sxs-lookup"><span data-stu-id="6ae8e-112">Assistant</span></span>|<span data-ttu-id="6ae8e-113">department</span><span class="sxs-lookup"><span data-stu-id="6ae8e-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="6ae8e-114">Estado de la base de datos original cuando la consultan User1 y User2.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="6ae8e-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="6ae8e-115">Alfreds</span></span>|<span data-ttu-id="6ae8e-116">Maria</span><span class="sxs-lookup"><span data-stu-id="6ae8e-116">Maria</span></span>|<span data-ttu-id="6ae8e-117">Ventas</span><span class="sxs-lookup"><span data-stu-id="6ae8e-117">Sales</span></span>|  
|<span data-ttu-id="6ae8e-118">User1 se prepara para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="6ae8e-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="6ae8e-119">Alfred</span></span>||<span data-ttu-id="6ae8e-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="6ae8e-120">Marketing</span></span>|  
|<span data-ttu-id="6ae8e-121">User2 ya ha enviado los cambios.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="6ae8e-122">Mary</span><span class="sxs-lookup"><span data-stu-id="6ae8e-122">Mary</span></span>|<span data-ttu-id="6ae8e-123">Servicio</span><span class="sxs-lookup"><span data-stu-id="6ae8e-123">Service</span></span>|  
  
 <span data-ttu-id="6ae8e-124">User1 decide resolver este conflicto haciendo que los valores más nuevos de la base de datos sobrescriban los valores actuales del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="6ae8e-125">Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, el resultado en la base de datos es el de la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae8e-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="6ae8e-126">Administrador</span><span class="sxs-lookup"><span data-stu-id="6ae8e-126">Manager</span></span>|<span data-ttu-id="6ae8e-127">Asistente</span><span class="sxs-lookup"><span data-stu-id="6ae8e-127">Assistant</span></span>|<span data-ttu-id="6ae8e-128">department</span><span class="sxs-lookup"><span data-stu-id="6ae8e-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="6ae8e-129">Nuevo estado tras la resolución del conflicto.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-129">New state after conflict resolution.</span></span>|<span data-ttu-id="6ae8e-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="6ae8e-130">Alfreds</span></span><br /><br /> <span data-ttu-id="6ae8e-131">(original)</span><span class="sxs-lookup"><span data-stu-id="6ae8e-131">(original)</span></span>|<span data-ttu-id="6ae8e-132">Mary</span><span class="sxs-lookup"><span data-stu-id="6ae8e-132">Mary</span></span><br /><br /> <span data-ttu-id="6ae8e-133">(de User2)</span><span class="sxs-lookup"><span data-stu-id="6ae8e-133">(from User2)</span></span>|<span data-ttu-id="6ae8e-134">Servicio</span><span class="sxs-lookup"><span data-stu-id="6ae8e-134">Service</span></span><br /><br /> <span data-ttu-id="6ae8e-135">(de User2)</span><span class="sxs-lookup"><span data-stu-id="6ae8e-135">(from User2)</span></span>|  
  
 <span data-ttu-id="6ae8e-136">El código de ejemplo siguiente muestra cómo sobrescribir los valores actuales del modelo de objetos con los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="6ae8e-137">(No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.)</span><span class="sxs-lookup"><span data-stu-id="6ae8e-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ae8e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ae8e-138">See also</span></span>

- [<span data-ttu-id="6ae8e-139">Cómo: Administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="6ae8e-139">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
