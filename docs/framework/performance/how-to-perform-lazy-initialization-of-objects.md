---
title: Procedimiento para realizar la inicialización diferida de objetos
description: Vea cómo realizar la inicialización diferida de objetos mediante la clase System. Lazy <T> . La inicialización diferida significa que no se crean objetos si no se necesitan nunca.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
ms.openlocfilehash: dbee0d8a5c3075ad7429feb92b87a566fdd35454
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309734"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a><span data-ttu-id="a4d2c-104">Procedimiento para realizar la inicialización diferida de objetos</span><span class="sxs-lookup"><span data-stu-id="a4d2c-104">How to: Perform Lazy Initialization of Objects</span></span>
<span data-ttu-id="a4d2c-105">La clase <xref:System.Lazy%601?displayProperty=nameWithType> simplifica el trabajo de creación de instancias e inicialización diferida de los objetos.</span><span class="sxs-lookup"><span data-stu-id="a4d2c-105">The <xref:System.Lazy%601?displayProperty=nameWithType> class simplifies the work of performing lazy initialization and instantiation of objects.</span></span> <span data-ttu-id="a4d2c-106">Al inicializar los objetos de manera diferida, se puede evitar su creación en caso de que no sean necesarios o se puede aplazar su inicialización hasta el primer acceso.</span><span class="sxs-lookup"><span data-stu-id="a4d2c-106">By initializing objects in a lazy manner, you can avoid having to create them at all if they are never needed, or you can postpone their initialization until they are first accessed.</span></span> <span data-ttu-id="a4d2c-107">Para obtener más información, vea [Inicialización diferida](lazy-initialization.md).</span><span class="sxs-lookup"><span data-stu-id="a4d2c-107">For more information, see [Lazy Initialization](lazy-initialization.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4d2c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4d2c-108">Example</span></span>  
 <span data-ttu-id="a4d2c-109">En el ejemplo siguiente, se muestra cómo inicializar un valor con <xref:System.Lazy%601>.</span><span class="sxs-lookup"><span data-stu-id="a4d2c-109">The following example shows how to initialize a value with <xref:System.Lazy%601>.</span></span> <span data-ttu-id="a4d2c-110">Es posible que la variable Lazy no sea necesaria, dependiendo de si otro código establece la variable `someCondition` en True o False.</span><span class="sxs-lookup"><span data-stu-id="a4d2c-110">Assume that the lazy variable might not be needed, depending on some other code that sets the `someCondition` variable to true or false.</span></span>  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
  {  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
  }  
```  
  
## <a name="example"></a><span data-ttu-id="a4d2c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4d2c-111">Example</span></span>  
 <span data-ttu-id="a4d2c-112">En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> para inicializar un tipo que solo es visible en la instancia de objeto actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a4d2c-112">The following example shows how to use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to initialize a type that is visible only to the current object instance on the current thread.</span></span>  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="a4d2c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4d2c-113">See also</span></span>

- <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>
- [<span data-ttu-id="a4d2c-114">Inicialización diferida</span><span class="sxs-lookup"><span data-stu-id="a4d2c-114">Lazy Initialization</span></span>](lazy-initialization.md)
