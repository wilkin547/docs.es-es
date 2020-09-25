---
title: Procedimiento para enviar los cambios a la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
ms.openlocfilehash: 5952cce5469d7a7e13e8b896f91ea1279fd62d8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197045"
---
# <a name="how-to-submit-changes-to-the-database"></a><span data-ttu-id="a8466-102">Procedimiento para enviar los cambios a la base de datos</span><span class="sxs-lookup"><span data-stu-id="a8466-102">How to: Submit Changes to the Database</span></span>

<span data-ttu-id="a8466-103">Con independencia de los cambios que se efectúen en los objetos, éstos sólo se realizan en las réplicas en memoria.</span><span class="sxs-lookup"><span data-stu-id="a8466-103">Regardless of how many changes you make to your objects, changes are made only to in-memory replicas.</span></span> <span data-ttu-id="a8466-104">Los cambios no se aplican a los datos reales de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a8466-104">You have made no changes to the actual data in the database.</span></span> <span data-ttu-id="a8466-105">Los cambios no se transmiten al servidor hasta que se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> explícitamente en <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="a8466-105">Your changes are not transmitted to the server until you explicitly call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="a8466-106">Al realizar esta llamada, <xref:System.Data.Linq.DataContext> intenta convertir los cambios a comandos SQL equivalentes.</span><span class="sxs-lookup"><span data-stu-id="a8466-106">When you make this call, the <xref:System.Data.Linq.DataContext> tries to translate your changes into equivalent SQL commands.</span></span> <span data-ttu-id="a8466-107">Puede usar su propia lógica personalizada para invalidar estas acciones, pero el orden de envío lo orquesta un servicio del <xref:System.Data.Linq.DataContext> conocido como *procesador de cambios*.</span><span class="sxs-lookup"><span data-stu-id="a8466-107">You can use your own custom logic to override these actions, but the order of submission is orchestrated by a service of the <xref:System.Data.Linq.DataContext> known as the *change processor*.</span></span> <span data-ttu-id="a8466-108">Todo ocurre en este orden:</span><span class="sxs-lookup"><span data-stu-id="a8466-108">The sequence of events is as follows:</span></span>  
  
1. <span data-ttu-id="a8466-109">Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examina el conjunto de objetos conocidos para determinar si se les han adjuntado nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="a8466-109">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] examines the set of known objects to determine whether new instances have been attached to them.</span></span> <span data-ttu-id="a8466-110">En caso afirmativo, estas nuevas instancias se agregan al conjunto de objetos con seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a8466-110">If they have, these new instances are added to the set of tracked objects.</span></span>  
  
2. <span data-ttu-id="a8466-111">Todos los objetos que tienen cambios pendientes se ordenan en una secuencia de objetos de acuerdo con las dependencias entre ellos.</span><span class="sxs-lookup"><span data-stu-id="a8466-111">All objects that have pending changes are ordered into a sequence of objects based on the dependencies between them.</span></span> <span data-ttu-id="a8466-112">Los objetos con cambios que dependen de otros objetos se ordenan según sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="a8466-112">Objects whose changes depend on other objects are sequenced after their dependencies.</span></span>  
  
3. <span data-ttu-id="a8466-113">Inmediatamente antes de que se transmitan los verdaderos cambios, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción para encapsular la serie de comandos individuales.</span><span class="sxs-lookup"><span data-stu-id="a8466-113">Immediately before any actual changes are transmitted, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a transaction to encapsulate the series of individual commands.</span></span>  
  
4. <span data-ttu-id="a8466-114">Los cambios en los objetos se convierten uno a uno en comandos SQL y se envían al servidor.</span><span class="sxs-lookup"><span data-stu-id="a8466-114">The changes to the objects are translated one by one to SQL commands and sent to the server.</span></span>  
  
 <span data-ttu-id="a8466-115">En este punto, cualquier error detectado por la base de datos hace que se detenga el proceso de envío, y se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="a8466-115">At this point, any errors detected by the database cause the submission process to stop, and an exception is raised.</span></span> <span data-ttu-id="a8466-116">Todos los cambios de la base de datos se revierten, como si no se hubiese enviado nada.</span><span class="sxs-lookup"><span data-stu-id="a8466-116">All changes to the database are rolled back as if no submissions ever occurred.</span></span> <span data-ttu-id="a8466-117"><xref:System.Data.Linq.DataContext> mantiene un registro completo de todos los cambios.</span><span class="sxs-lookup"><span data-stu-id="a8466-117">The <xref:System.Data.Linq.DataContext> still has a full recording of all changes.</span></span> <span data-ttu-id="a8466-118">Por lo tanto, se puede intentar corregir el problema y llamar de nuevo a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a8466-118">You can therefore try to correct the problem and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> again, as in the code example that follows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8466-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8466-119">Example</span></span>  

 <span data-ttu-id="a8466-120">Cuando la transacción relacionada con el envío se completa correctamente, <xref:System.Data.Linq.DataContext> recibe los cambios de los objetos sin tener en cuenta la información de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="a8466-120">When the transaction around the submission is completed successfully, the <xref:System.Data.Linq.DataContext> accepts the changes to the objects by ignoring the change-tracking information.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a8466-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8466-121">See also</span></span>

- [<span data-ttu-id="a8466-122">Procedimiento para detectar y resolver envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="a8466-122">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)
- [<span data-ttu-id="a8466-123">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="a8466-123">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="a8466-124">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8466-124">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="a8466-125">Realizar y enviar cambios de datos</span><span class="sxs-lookup"><span data-stu-id="a8466-125">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
