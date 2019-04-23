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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc8cd20a4183ffd002f1399b6b50c8956208a21b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173685"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="580d8-102">Proteger control de excepciones</span><span class="sxs-lookup"><span data-stu-id="580d8-102">Securing Exception Handling</span></span>
<span data-ttu-id="580d8-103">En Visual C++ y Visual Basic, se ejecuta una expresión de filtro más arriba en la pila antes de cualquier **finalmente** instrucción.</span><span class="sxs-lookup"><span data-stu-id="580d8-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="580d8-104">El **catch** bloque asociado con ese filtro se ejecuta después el **finalmente** instrucción.</span><span class="sxs-lookup"><span data-stu-id="580d8-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="580d8-105">Para obtener más información, consulte [excepciones filtradas por el usuario](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="580d8-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="580d8-106">Esta sección examinan las implicaciones de seguridad de este pedido.</span><span class="sxs-lookup"><span data-stu-id="580d8-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="580d8-107">Considere el siguiente ejemplo de pseudocódigo que ilustra el orden en que las instrucciones de filtro y **finalmente** ejecutar las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="580d8-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="580d8-108">Este código imprime lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="580d8-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="580d8-109">El filtro se ejecuta antes que la **finalmente** instrucción, por lo que se pueden introducir problemas de seguridad en todo aquello que hace que un estado cambie a aprovechar la ejecución de otro código.</span><span class="sxs-lookup"><span data-stu-id="580d8-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="580d8-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="580d8-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="580d8-111">Este pseudocódigo permite que un filtro situado más arriba en la pila para ejecutar código arbitrario.</span><span class="sxs-lookup"><span data-stu-id="580d8-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="580d8-112">Otros ejemplos de operaciones que pueden tener un efecto similar son temporal suplantación de identidad de otro, un marcador interno que omita alguna comprobación de seguridad, o cambiar la referencia cultural asociada al subproceso.</span><span class="sxs-lookup"><span data-stu-id="580d8-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="580d8-113">La solución recomendada es introducir un controlador de excepciones para aislar los cambios del código para el estado del subproceso de bloques de filtro de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="580d8-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="580d8-114">Sin embargo, es importante que el controlador de excepciones se ha introducido correctamente o no se corregirá este problema.</span><span class="sxs-lookup"><span data-stu-id="580d8-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="580d8-115">En el ejemplo siguiente se cambia la referencia cultural de interfaz de usuario, pero cualquier tipo de cambio de estado de subproceso podría mostrarse de forma similar.</span><span class="sxs-lookup"><span data-stu-id="580d8-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="580d8-116">En este caso es la solución adecuada ajustar la existente **intente**/**finalmente** bloquear un **intente**/**catch** bloque.</span><span class="sxs-lookup"><span data-stu-id="580d8-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="580d8-117">Introducir un **catch throw** cláusula existentes **intente**/**finalmente** bloque no soluciona el problema, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="580d8-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="580d8-118">Esto no soluciona el problema porque el **finalmente** instrucción no se ha ejecutado antes el `FilterFunc` obtiene control.</span><span class="sxs-lookup"><span data-stu-id="580d8-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="580d8-119">En el ejemplo siguiente se corrige el problema asegurándose de que el **finalmente** cláusula ha ejecutado antes de generar una excepción de los bloques de filtro de excepción de los llamadores.</span><span class="sxs-lookup"><span data-stu-id="580d8-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="580d8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="580d8-120">See also</span></span>

- [<span data-ttu-id="580d8-121">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="580d8-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
