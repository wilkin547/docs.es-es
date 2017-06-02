---
title: "Securing Exception Handling | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "code security, exception handling"
  - "security [.NET Framework], exception handling"
  - "secure coding, exception handling"
  - "exception handling, security"
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Securing Exception Handling
En C\+\+ y Visual Basic, se ejecuta una expresión de filtro más arriba de la pila antes de cualquier instrucción **finally**.  El bloque **catch** asociado con ese filtro se ejecuta después de la instrucción **finally**.  Para obtener más información, vea [Utilizar excepciones filtradas por el usuario](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).  En esta sección se analizan las repercusiones de seguir este orden en la seguridad.  Observe el siguiente ejemplo de pseudocódigo que ilustra el orden en que se ejecutan las expresiones de filtro y las instrucciones **finally**.  
  
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
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 El filtro se ejecuta antes de la instrucción **finally**, así que es posible introducir problemas de seguridad en todo aquello que produce un cambio de estado y permite aprovechar la ejecución de otro código.  Por ejemplo:  
  
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
  
 Este pseudocódigo permite que un filtro situado más arriba de la pila ejecute un código arbitrario.  Entre los ejemplos de operaciones que pueden tener un efecto similar está la suplantación provisional de otra identidad mediante un marcador interno que omita alguna comprobación de seguridad o cambiando la referencia cultural asociada con el subproceso.  La solución más recomendable es introducir un controlador de excepciones para aislar los cambios del código en el estado de subproceso de los bloques de filtro de los llamadores.  Sin embargo, es importante introducir correctamente el controlador de excepciones o no se solucionará este problema.  En el ejemplo siguiente se cambia la referencia cultural de la interfaz de usuario, aunque se puede exponer de forma similar cualquier clase de cambio de estado de subproceso.  
  
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
  
 La solución adecuada para este caso es incluir el bloque **try**\/**finally** existente en un bloque **try**\/**catch**.  El problema no se soluciona si únicamente se introduce una cláusula **catch\-throw** en el bloque **try**\/**finally** existente, como se muestra en el ejemplo siguiente.  
  
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
  
 Esto no soluciona el problema debido a que la instrucción **finally** no se ha ejecutado antes de que `FilterFunc` obtenga el control.  
  
 En el siguiente ejemplo el problema se soluciona si se garantiza que la cláusula **finally** se ha ejecutado antes de generar una excepción arriba de los bloques de filtro de la excepción los llamadores.  
  
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
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)