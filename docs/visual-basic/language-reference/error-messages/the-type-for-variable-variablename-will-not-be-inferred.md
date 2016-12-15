---
title: "El tipo de la variable &#39;&lt;nombreDeVariable&gt;&#39; no se inferir&#225; porque est&#225; enlazada a un campo en un &#225;mbito de inclusi&#243;n. | Microsoft Docs"
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
  - "vbc42110"
  - "bc42110"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42110"
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El tipo de la variable &#39;&lt;nombreDeVariable&gt;&#39; no se inferir&#225; porque est&#225; enlazada a un campo en un &#225;mbito de inclusi&#243;n.
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El tipo de la variable '\<nombreDeVariable\>' no se inferirá porque está enlazada a un campo en un ámbito de inclusión.Cambie el nombre de '\<nombreDeVariable\>' o utilice el nombre completo \(por ejemplo, 'Me.nombreDeVariable' o 'MiBase.nombreDeVariable'\).  
  
 Una variable de control de bucle en su código tiene el mismo nombre que un campo de la clase u otro ámbito de inclusión.  Dado que la variable de control se utiliza sin una cláusula `As`, se enlaza al campo en el ámbito de inclusión y el compilador no crea una nueva variable para ella ni infiere su tipo.  
  
 En el ejemplo siguiente, `Index`, es decir, la variable de control en la instrucción `For`, se enlaza al campo `Index` de la clase `Customer`.  El compilador no crea una nueva variable para la variable de control `Index` ni infiere su tipo.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
  
```  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42110  
  
### Para resolver esta advertencia  
  
-   Convierta la variable de control de bucle en local cambiando su nombre por un identificador que tampoco sea el nombre de un campo de la clase.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Asegúrese de que la variable de control de bucle se enlaza al campo de clase agregando el prefijo `Me.` al nombre de variable.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   En lugar de basarse en la inferencia de tipo local, use una cláusula `As` para especificar un tipo para la variable de control de bucle.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## Ejemplo  
 El código siguiente muestra el ejemplo anterior con la primera corrección en contexto.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## Vea también  
 [Option Infer \(instrucción\)](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Cómo: Hacer referencia a la instancia actual de un objeto](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)