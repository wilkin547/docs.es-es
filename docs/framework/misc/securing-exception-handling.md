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
ms.openlocfilehash: c7643bb34da0cbcbd267fc90e6294bc0b565985e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855782"
---
# <a name="securing-exception-handling"></a>Proteger control de excepciones

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

En Visual C++ y Visual Basic, una expresión de filtro más arriba en la pila se ejecuta antes que cualquier `finally` instrucción. El bloque **catch** asociado a ese filtro se ejecuta después de la `finally` instrucción. Para obtener más información, consulte [uso de excepciones filtradas por el usuario](../../standard/exceptions/using-user-filtered-exception-handlers.md). En esta sección se examinan las implicaciones de seguridad de este orden. Considere el siguiente ejemplo de pseudocódigo que ilustra el orden en el que se ejecutan las instrucciones y instrucciones de filtro `finally` .  
  
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
  
 Este código imprime lo siguiente.  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 El filtro se ejecuta antes de la `finally` instrucción, por lo que los problemas de seguridad pueden introducirse en cualquier cosa que realice un cambio de estado en el que la ejecución de otro código podría aprovecharse. Por ejemplo:  
  
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
  
 Este pseudocódigo permite un filtro más arriba en la pila para ejecutar código arbitrario. Otros ejemplos de operaciones que tendrían un efecto similar son la suplantación temporal de otra identidad, el establecimiento de una marca interna que omita alguna comprobación de seguridad o el cambio de la referencia cultural asociada al subproceso. La solución recomendada consiste en introducir un controlador de excepciones para aislar los cambios del código en el estado de subprocesos de los bloques de filtro de los llamadores. Sin embargo, es importante introducir correctamente el controlador de excepciones o este problema no se solucionará. En el ejemplo siguiente se cambia la referencia cultural de la interfaz de usuario, pero cualquier tipo de cambio de estado del subproceso podría estar expuesto de forma similar.  
  
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
  
 En este caso, la corrección correcta es ajustar el bloque **try** / **Finally** existente en un bloque **try** / **catch** . Simplemente la introducción de una cláusula **catch-Throw** en el bloque **try** / **Finally** existente no soluciona el problema, tal como se muestra en el ejemplo siguiente.  
  
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
  
 Esto no soluciona el problema porque la `finally` instrucción no se ha ejecutado antes del `FilterFunc` control obtiene.  
  
 En el ejemplo siguiente se corrige el problema asegurándose de que la `finally` cláusula se ha ejecutado antes de ofrecer una excepción a los bloques de filtro de excepciones de los llamadores.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
