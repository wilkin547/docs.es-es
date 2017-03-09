---
title: "C&#243;mo: Usar expresiones lambda fuera de LINQ (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "expresiones lambda [C#], fuera de LINQ"
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# C&#243;mo: Usar expresiones lambda fuera de LINQ (Gu&#237;a de programaci&#243;n de C#)
Las expresiones lambda no se limitan a las consultas de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  Puede utilizarlas en cualquier parte en la que se espera un valor de delegado, es decir, dondequiera que se pueda utilizar un método anónimo.  El ejemplo siguiente muestra cómo utilizar una expresión lambda en un controlador de eventos de formularios Windows Forms.  Observe que los tipos de las entradas \(<xref:System.Object> y <xref:System.Windows.Forms.MouseEventArgs>\) los deduce el compilador y no tienen que especificarse explícitamente en los parámetros de entrada lambda.  
  
## Ejemplo  
  
```  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## Vea también  
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)