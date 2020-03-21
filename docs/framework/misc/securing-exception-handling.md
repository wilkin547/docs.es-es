---
title: Proteger control de excepciones
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: ad27e62197f6fdaa6b5e706f4ae02c03fecae9f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181136"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="eadea-102">Proteger control de excepciones</span><span class="sxs-lookup"><span data-stu-id="eadea-102">Securing Exception Handling</span></span>
<span data-ttu-id="eadea-103">En Visual C++ y Visual Basic, una expresión de filtro más arriba de la pila se ejecuta antes de cualquier instrucción **finally.**</span><span class="sxs-lookup"><span data-stu-id="eadea-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="eadea-104">El bloque **catch** asociado a ese filtro se ejecuta después de la instrucción **finally.**</span><span class="sxs-lookup"><span data-stu-id="eadea-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="eadea-105">Para obtener más información, consulte Uso de [excepciones filtradas por](../../standard/exceptions/using-user-filtered-exception-handlers.md)el usuario .</span><span class="sxs-lookup"><span data-stu-id="eadea-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="eadea-106">En esta sección se examinan las implicaciones de seguridad de este orden.</span><span class="sxs-lookup"><span data-stu-id="eadea-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="eadea-107">Considere el siguiente ejemplo de pseudocódigo que ilustra el orden en que se ejecutan las instrucciones filter y **finally.**</span><span class="sxs-lookup"><span data-stu-id="eadea-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()
{  
    try
    {  
        Sub();  
    }
    except (Filter())
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()
{  
    try
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }
    finally
    {  
        Console.WriteLine("finally");  
    }  
}
```  
  
 <span data-ttu-id="eadea-108">Este código imprime lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eadea-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="eadea-109">El filtro se ejecuta antes de la instrucción **finally,** por lo que los problemas de seguridad se pueden introducir mediante cualquier cosa que realice un cambio de estado en el que la ejecución de otro código podría aprovecharse.</span><span class="sxs-lookup"><span data-stu-id="eadea-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="eadea-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eadea-110">For example:</span></span>  
  
```cpp  
try
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and
    // so on) that could be exploited if malicious
    // code ran before state is restored.  
    Do_some_work();  
}
finally
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="eadea-111">Este pseudocódigo permite que un filtro más arriba de la pila ejecute código arbitrario.</span><span class="sxs-lookup"><span data-stu-id="eadea-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="eadea-112">Otros ejemplos de operaciones que tendrían un efecto similar son la suplantación temporal de otra identidad, la configuración de una marca interna que omite alguna comprobación de seguridad o el cambio de la referencia cultural asociada al subproceso.</span><span class="sxs-lookup"><span data-stu-id="eadea-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="eadea-113">La solución recomendada es introducir un controlador de excepciones para aislar los cambios del código en el estado del subproceso de los bloques de filtro de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="eadea-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="eadea-114">Sin embargo, es importante que el controlador de excepciones se introduzca correctamente o que este problema no se solucione.</span><span class="sxs-lookup"><span data-stu-id="eadea-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="eadea-115">En el ejemplo siguiente se cambia la referencia cultural de la interfaz de usuario, pero cualquier tipo de cambio de estado de subproceso podría exponerse de forma similar.</span><span class="sxs-lookup"><span data-stu-id="eadea-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="eadea-116">La corrección correcta en este caso es ajustar el bloque **try**/**finally** existente en un bloque **try**/**catch.**</span><span class="sxs-lookup"><span data-stu-id="eadea-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="eadea-117">Simplemente introducir una cláusula **catch-throw** en el bloque**finally** **try**/existente no soluciona el problema, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eadea-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="eadea-118">Esto no soluciona el **finally** problema porque la `FilterFunc` instrucción finally no se ha ejecutado antes de que gets control.</span><span class="sxs-lookup"><span data-stu-id="eadea-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="eadea-119">En el ejemplo siguiente se corrige el problema asegurándose de que la cláusula **finally** se ha ejecutado antes de ofrecer una excepción a los bloques de filtro de excepción de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="eadea-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try
    {  
        try
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="eadea-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eadea-120">See also</span></span>

- [<span data-ttu-id="eadea-121">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="eadea-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
