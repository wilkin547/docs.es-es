---
title: 'Cómo: Usar expresiones lambda fuera de LINQ (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: eb9fea64b8aeb96a880b7e177673c1316b7aa4c1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45639177"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a>Cómo: Usar expresiones lambda fuera de LINQ (Guía de programación de C#)
Las expresiones lambda no están limitadas a las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Se pueden usar en cualquier lugar en que se espere un valor de delegado, es decir, dondequiera que se puede usar un método anónimo. En el ejemplo siguiente se muestra cómo usar una expresión lambda en un controlador de eventos de Windows Forms. Observe que los tipos de las entradas (<xref:System.Object> y <xref:System.Windows.Forms.MouseEventArgs>) los deduce el compilador y no tienen que especificarse explícitamente en los parámetros de entrada lambda.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
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
  
## <a name="see-also"></a>Vea también

- [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
