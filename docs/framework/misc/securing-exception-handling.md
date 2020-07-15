---
title: Proteger control de excepciones
description: Vea cómo hacer que el control de excepciones sea seguro en el código .NET. Revise el orden en el que se ejecuta el código si hay instrucciones try, Except, Catch y Finally.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: 73597f83d7236cd48a18a891c987b4f5d7e1723d
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309045"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="cd813-104">Proteger control de excepciones</span><span class="sxs-lookup"><span data-stu-id="cd813-104">Securing Exception Handling</span></span>
<span data-ttu-id="cd813-105">En Visual C++ y Visual Basic, una expresión de filtro más arriba en la pila se ejecuta antes que cualquier `finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="cd813-105">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any `finally` statement.</span></span> <span data-ttu-id="cd813-106">El bloque **catch** asociado a ese filtro se ejecuta después de la `finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="cd813-106">The **catch** block associated with that filter runs after the `finally` statement.</span></span> <span data-ttu-id="cd813-107">Para obtener más información, consulte [uso de excepciones filtradas por el usuario](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="cd813-107">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="cd813-108">En esta sección se examinan las implicaciones de seguridad de este orden.</span><span class="sxs-lookup"><span data-stu-id="cd813-108">This section examines the security implications of this order.</span></span> <span data-ttu-id="cd813-109">Considere el siguiente ejemplo de pseudocódigo que ilustra el orden en el que se ejecutan las instrucciones y instrucciones de filtro `finally` .</span><span class="sxs-lookup"><span data-stu-id="cd813-109">Consider the following pseudocode example that illustrates the order in which filter statements and `finally` statements run.</span></span>  
  
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
  
 <span data-ttu-id="cd813-110">Este código imprime lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd813-110">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="cd813-111">El filtro se ejecuta antes de la `finally` instrucción, por lo que los problemas de seguridad pueden introducirse en cualquier cosa que realice un cambio de estado en el que la ejecución de otro código podría aprovecharse.</span><span class="sxs-lookup"><span data-stu-id="cd813-111">The filter runs before the `finally` statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="cd813-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cd813-112">For example:</span></span>  
  
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
  
 <span data-ttu-id="cd813-113">Este pseudocódigo permite un filtro más arriba en la pila para ejecutar código arbitrario.</span><span class="sxs-lookup"><span data-stu-id="cd813-113">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="cd813-114">Otros ejemplos de operaciones que tendrían un efecto similar son la suplantación temporal de otra identidad, el establecimiento de una marca interna que omita alguna comprobación de seguridad o el cambio de la referencia cultural asociada al subproceso.</span><span class="sxs-lookup"><span data-stu-id="cd813-114">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="cd813-115">La solución recomendada consiste en introducir un controlador de excepciones para aislar los cambios del código en el estado de subprocesos de los bloques de filtro de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="cd813-115">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="cd813-116">Sin embargo, es importante introducir correctamente el controlador de excepciones o este problema no se solucionará.</span><span class="sxs-lookup"><span data-stu-id="cd813-116">However, it's important to properly introduce the exception handler or this problem won't be fixed.</span></span> <span data-ttu-id="cd813-117">En el ejemplo siguiente se cambia la referencia cultural de la interfaz de usuario, pero cualquier tipo de cambio de estado del subproceso podría estar expuesto de forma similar.</span><span class="sxs-lookup"><span data-stu-id="cd813-117">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="cd813-118">En este caso, la corrección correcta es ajustar el bloque **try** / **Finally** existente en un bloque **try** / **catch** .</span><span class="sxs-lookup"><span data-stu-id="cd813-118">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="cd813-119">Simplemente la introducción de una cláusula **catch-Throw** en el bloque **try** / **Finally** existente no soluciona el problema, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd813-119">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="cd813-120">Esto no soluciona el problema porque la `finally` instrucción no se ha ejecutado antes del `FilterFunc` control obtiene.</span><span class="sxs-lookup"><span data-stu-id="cd813-120">This does not fix the problem because the `finally` statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="cd813-121">En el ejemplo siguiente se corrige el problema asegurándose de que la `finally` cláusula se ha ejecutado antes de ofrecer una excepción a los bloques de filtro de excepciones de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="cd813-121">The following example fixes the problem by ensuring that the `finally` clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd813-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd813-122">See also</span></span>

- [<span data-ttu-id="cd813-123">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="cd813-123">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
