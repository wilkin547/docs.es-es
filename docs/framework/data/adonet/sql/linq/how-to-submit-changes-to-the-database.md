---
title: "Cómo: Enviar cambios a la base de datos"
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
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf1f9c7982cf9f328fe060266762658ab9693c2e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-submit-changes-to-the-database"></a><span data-ttu-id="fb46d-102">Cómo: Enviar cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="fb46d-102">How to: Submit Changes to the Database</span></span>
<span data-ttu-id="fb46d-103">Con independencia de los cambios que se efectúen en los objetos, éstos sólo se realizan en las réplicas en memoria.</span><span class="sxs-lookup"><span data-stu-id="fb46d-103">Regardless of how many changes you make to your objects, changes are made only to in-memory replicas.</span></span> <span data-ttu-id="fb46d-104">Los cambios no se aplican a los datos reales de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fb46d-104">You have made no changes to the actual data in the database.</span></span> <span data-ttu-id="fb46d-105">Los cambios no se transmiten al servidor hasta que se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> explícitamente en <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="fb46d-105">Your changes are not transmitted to the server until you explicitly call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="fb46d-106">Al realizar esta llamada, <xref:System.Data.Linq.DataContext> intenta convertir los cambios a comandos SQL equivalentes.</span><span class="sxs-lookup"><span data-stu-id="fb46d-106">When you make this call, the <xref:System.Data.Linq.DataContext> tries to translate your changes into equivalent SQL commands.</span></span> <span data-ttu-id="fb46d-107">Puede usar su propia lógica personalizada para invalidar estas acciones, pero el orden de envío se organiza por un servicio de la <xref:System.Data.Linq.DataContext> conocido como el *cambiar procesador*.</span><span class="sxs-lookup"><span data-stu-id="fb46d-107">You can use your own custom logic to override these actions, but the order of submission is orchestrated by a service of the <xref:System.Data.Linq.DataContext> known as the *change processor*.</span></span> <span data-ttu-id="fb46d-108">Todo ocurre en este orden:</span><span class="sxs-lookup"><span data-stu-id="fb46d-108">The sequence of events is as follows:</span></span>  
  
1.  <span data-ttu-id="fb46d-109">Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examina el conjunto de objetos conocidos para determinar si se les han adjuntado nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="fb46d-109">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examines the set of known objects to determine whether new instances have been attached to them.</span></span> <span data-ttu-id="fb46d-110">En caso afirmativo, estas nuevas instancias se agregan al conjunto de objetos con seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fb46d-110">If they have, these new instances are added to the set of tracked objects.</span></span>  
  
2.  <span data-ttu-id="fb46d-111">Todos los objetos que tienen cambios pendientes se ordenan en una secuencia de objetos de acuerdo con las dependencias entre ellos.</span><span class="sxs-lookup"><span data-stu-id="fb46d-111">All objects that have pending changes are ordered into a sequence of objects based on the dependencies between them.</span></span> <span data-ttu-id="fb46d-112">Los objetos con cambios que dependen de otros objetos se ordenan según sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="fb46d-112">Objects whose changes depend on other objects are sequenced after their dependencies.</span></span>  
  
3.  <span data-ttu-id="fb46d-113">Inmediatamente antes de que se transmitan los verdaderos cambios, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción para encapsular la serie de comandos individuales.</span><span class="sxs-lookup"><span data-stu-id="fb46d-113">Immediately before any actual changes are transmitted, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a transaction to encapsulate the series of individual commands.</span></span>  
  
4.  <span data-ttu-id="fb46d-114">Los cambios en los objetos se convierten uno a uno en comandos SQL y se envían al servidor.</span><span class="sxs-lookup"><span data-stu-id="fb46d-114">The changes to the objects are translated one by one to SQL commands and sent to the server.</span></span>  
  
 <span data-ttu-id="fb46d-115">En este punto, cualquier error detectado por la base de datos hace que se detenga el proceso de envío, y se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="fb46d-115">At this point, any errors detected by the database cause the submission process to stop, and an exception is raised.</span></span> <span data-ttu-id="fb46d-116">Todos los cambios de la base de datos se revierten, como si no se hubiese enviado nada.</span><span class="sxs-lookup"><span data-stu-id="fb46d-116">All changes to the database are rolled back as if no submissions ever occurred.</span></span> <span data-ttu-id="fb46d-117"><xref:System.Data.Linq.DataContext> mantiene un registro completo de todos los cambios.</span><span class="sxs-lookup"><span data-stu-id="fb46d-117">The <xref:System.Data.Linq.DataContext> still has a full recording of all changes.</span></span> <span data-ttu-id="fb46d-118">Por lo tanto, se puede intentar corregir el problema y llamar de nuevo a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="fb46d-118">You can therefore try to correct the problem and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> again, as in the code example that follows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb46d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb46d-119">Example</span></span>  
 <span data-ttu-id="fb46d-120">Cuando la transacción relacionada con el envío se completa correctamente, <xref:System.Data.Linq.DataContext> recibe los cambios de los objetos sin tener en cuenta la información de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="fb46d-120">When the transaction around the submission is completed successfully, the <xref:System.Data.Linq.DataContext> accepts the changes to the objects by ignoring the change-tracking information.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fb46d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb46d-121">See Also</span></span>  
 [<span data-ttu-id="fb46d-122">Detección y resolución de envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="fb46d-122">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 [<span data-ttu-id="fb46d-123">Administración de conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="fb46d-123">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="fb46d-124">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb46d-124">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="fb46d-125">Realización y envío de cambios de datos</span><span class="sxs-lookup"><span data-stu-id="fb46d-125">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
