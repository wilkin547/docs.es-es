---
title: 'Cómo: Habilitar el modo de seguimiento de subproceso en el bloqueo SpinLock'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3b9671c10889287bc22d64df1fb5c3a2984bd55
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44195285"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="45c32-102">Cómo: Habilitar el modo de seguimiento de subproceso en el bloqueo SpinLock</span><span class="sxs-lookup"><span data-stu-id="45c32-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="45c32-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> es un bloqueo de exclusión mutua de bajo nivel que se puede usar para escenarios que tienen tiempos de espera muy cortos.</span><span class="sxs-lookup"><span data-stu-id="45c32-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="45c32-104"><xref:System.Threading.SpinLock> no es reentrante.</span><span class="sxs-lookup"><span data-stu-id="45c32-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="45c32-105">Una vez que el subproceso activa el bloqueo, debe desactivarlo correctamente para volver a entrar.</span><span class="sxs-lookup"><span data-stu-id="45c32-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="45c32-106">Por lo general, cualquier intento de reentrada en el bloqueo produciría un interbloqueo, y los interbloqueos pueden ser muy difíciles de depurar.</span><span class="sxs-lookup"><span data-stu-id="45c32-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="45c32-107">Como ayuda para el desarrollo, <xref:System.Threading.SpinLock?displayProperty=nameWithType> admite un modo de seguimiento de subprocesos que provoca la emisión de una excepción cuando un subproceso intenta reentrar en un bloqueo que ya tenía.</span><span class="sxs-lookup"><span data-stu-id="45c32-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="45c32-108">Esto le permite que localizar con mayor facilidad el punto en el que el bloqueo no se cerró correctamente.</span><span class="sxs-lookup"><span data-stu-id="45c32-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="45c32-109">Puede activar el modo de seguimiento de subprocesos mediante el uso del constructor <xref:System.Threading.SpinLock> que toma un valor booleano de entrada y pasando un argumento de `true`.</span><span class="sxs-lookup"><span data-stu-id="45c32-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="45c32-110">Después de completar las fases de desarrollo y pruebas, desactive el modo de seguimiento de subprocesos para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="45c32-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45c32-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45c32-111">Example</span></span>  
 <span data-ttu-id="45c32-112">En el ejemplo siguiente se muestra el modo de seguimiento de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="45c32-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="45c32-113">Las líneas que salen correctamente del bloqueo están comentadas para simular un error de código que genera uno de los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="45c32-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="45c32-114">Se produce una excepción si <xref:System.Threading.SpinLock> se creó mediante un argumento de `true` (`True` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="45c32-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="45c32-115">Se produce un interbloqueo si <xref:System.Threading.SpinLock> se creó mediante un argumento de `false` (`False` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="45c32-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="45c32-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="45c32-116">See also</span></span>

- [<span data-ttu-id="45c32-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="45c32-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
