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
# <a name="securing-exception-handling"></a>Proteger control de excepciones
En Visual C++ y Visual Basic, una expresión de filtro más arriba de la pila se ejecuta antes de cualquier instrucción **finally.** El bloque **catch** asociado a ese filtro se ejecuta después de la instrucción **finally.** Para obtener más información, consulte Uso de [excepciones filtradas por](../../standard/exceptions/using-user-filtered-exception-handlers.md)el usuario . En esta sección se examinan las implicaciones de seguridad de este orden. Considere el siguiente ejemplo de pseudocódigo que ilustra el orden en que se ejecutan las instrucciones filter y **finally.**  
  
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
  
 El filtro se ejecuta antes de la instrucción **finally,** por lo que los problemas de seguridad se pueden introducir mediante cualquier cosa que realice un cambio de estado en el que la ejecución de otro código podría aprovecharse. Por ejemplo:  
  
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
  
 Este pseudocódigo permite que un filtro más arriba de la pila ejecute código arbitrario. Otros ejemplos de operaciones que tendrían un efecto similar son la suplantación temporal de otra identidad, la configuración de una marca interna que omite alguna comprobación de seguridad o el cambio de la referencia cultural asociada al subproceso. La solución recomendada es introducir un controlador de excepciones para aislar los cambios del código en el estado del subproceso de los bloques de filtro de los llamadores. Sin embargo, es importante que el controlador de excepciones se introduzca correctamente o que este problema no se solucione. En el ejemplo siguiente se cambia la referencia cultural de la interfaz de usuario, pero cualquier tipo de cambio de estado de subproceso podría exponerse de forma similar.  
  
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
  
 La corrección correcta en este caso es ajustar el bloque **try**/**finally** existente en un bloque **try**/**catch.** Simplemente introducir una cláusula **catch-throw** en el bloque**finally** **try**/existente no soluciona el problema, como se muestra en el ejemplo siguiente.  
  
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
  
 Esto no soluciona el **finally** problema porque la `FilterFunc` instrucción finally no se ha ejecutado antes de que gets control.  
  
 En el ejemplo siguiente se corrige el problema asegurándose de que la cláusula **finally** se ha ejecutado antes de ofrecer una excepción a los bloques de filtro de excepción de los llamadores.  
  
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
