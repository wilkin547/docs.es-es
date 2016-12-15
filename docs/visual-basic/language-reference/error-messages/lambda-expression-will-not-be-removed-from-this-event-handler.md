---
title: "La expresi&#243;n lambda no se quitar&#225; de este controlador de eventos | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42326"
  - "vbc42326"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42326"
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La expresi&#243;n lambda no se quitar&#225; de este controlador de eventos
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La expresión lambda no se quitará de este controlador de eventos.Asigne la expresión lambda a una variable y utilice la variable para agregar y quitar el evento.  
  
 Cuando se utilizan expresiones lambda con controladores de eventos, es posible que no vea el comportamiento que espera.  El compilador genera un nuevo método para cada definición de la expresión lambda, incluso si son idénticos.  Por consiguiente, el código siguiente muestra `False`.  
  
```vb#  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 Cuando se utilizan expresiones lambda con controladores de eventos, pueden producirse resultados inesperados.  En el ejemplo siguiente, la instrucción `RemoveHandler` no quita la expresión lambda agregada por `AddHandler`.  
  
```vb#  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42326  
  
### Para corregir este error  
  
-   Para evitar la advertencia y quitar la expresión lambda, asigne la expresión lambda a una variable y utilice la variable en las instrucciones `RemoveHandler` y `AddHandler`, como se muestra en el ejemplo siguiente.  
  
    ```vb#  
    Module Module1  
  
        Event ProcessInteger(ByVal x As Integer)  
  
        Dim PrintHandler As ProcessIntegerEventHandler  
  
        Sub Main()  
  
            ' Assign the lambda expression to a variable.  
            PrintHandler = Function(m As Integer) m  
  
            ' Use the variable to add the listener.  
            AddHandler ProcessInteger, PrintHandler  
  
            ' Use the variable again when you want to remove the listener.  
            RemoveHandler ProcessInteger, PrintHandler  
  
        End Sub  
    End Module  
    ```  
  
## Vea también  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)