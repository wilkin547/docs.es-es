---
title: "lock (Instrucci&#243;n, Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "lock_CSharpKeyword"
  - "lock"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lock (palabra clave) [C#]"
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
caps.handback.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# lock (Instrucci&#243;n, Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `lock` marca un bloque de instrucciones como una sección crucial, para lo cual utiliza el bloqueo de exclusión mutua de un objeto, la ejecución de una instrucción y, posteriormente, la liberación del bloqueo.  El ejemplo siguiente incluye un fragmento de `lock` .  
  
```  
  
class Account  
{  
    decimal balance;  
    private Object thisLock = new Object();  
  
    public void Withdraw(decimal amount)  
    {  
        lock (thisLock)  
        {  
            if (amount > balance)  
            {  
                throw new Exception("Insufficient funds");  
            }  
            balance -= amount;  
        }  
    }  
}  
  
```  
  
 Para obtener más información, vea [Sincronización de subprocesos](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Comentarios  
 La palabra clave `lock` garantiza que un subproceso no va a entrar en una sección crítica del código mientras otro subproceso se encuentre ya en esta sección.  Si otro subproceso intenta entrar en un código bloqueado, esperará, o se bloqueará, hasta que el objeto se libere.  
  
 En la sección [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md) se describe el subprocesamiento.  
  
 La palabra clave `lock` llama a <xref:System.Threading.Monitor.Enter%2A> al principio del bloque y a <xref:System.Threading.Monitor.Exit%2A> al final del bloque.  Se produce <xref:System.Threading.ThreadInterruptedException> si <xref:System.Threading.Thread.Interrupt%2A> interrumpe un subproceso que está esperando para escribir un fragmento de `lock` .  
  
 En general evite bloquear un tipo `public` o instancias que estén fuera del control de su código.  Las construcciones comunes `lock (this)`, `lock (typeof (MyType))` y `lock ("myLock")` incumplen esta instrucción:  
  
-   `lock (this)` se convierte en un problema si la instancia es accesible públicamente.  
  
-   `lock (typeof (MyType))` se convierte en un problema si `MyType` es accesible públicamente.  
  
-   `lock("myLock")` se convierte en un problema puesto que cualquier otro código del proceso que utilice la misma cadena compartirá el mismo bloqueo.  
  
 El procedimiento recomendado es definir un objeto un objeto `private` para realizar el bloqueo o una variable de objeto `private static` para proteger los datos comunes a todas las instancias.  
  
 No puede utilizar la palabra clave de [espera](../../../csharp/language-reference/keywords/await.md) en el cuerpo de un fragmento de `lock` .  
  
## Ejemplo  
 El siguiente ejemplo muestra un uso simple de subprocesos sin bloquear en C\#.  
  
 [!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## Ejemplo  
 El siguiente ejemplo utiliza subprocesos y `lock`.  Con el uso de la instrucción `lock`, el bloque de instrucciones se convierte en una sección crítica y `balance` nunca tomará un valor negativo.  
  
 [!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.Reflection.MethodImplAttributes>   
 <xref:System.Threading.Mutex>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de instrucciones](../../../csharp/language-reference/keywords/statement-keywords.md)   
 [Monitores](../Topic/Monitors.md)   
 [Interlocked Operations](../Topic/Interlocked%20Operations.md)   
 [AutoResetEvent](../Topic/AutoResetEvent.md)   
 [Sincronización de subprocesos](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)