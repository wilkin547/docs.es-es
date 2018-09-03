---
title: 'Cómo: Usar expresiones lambda fuera de LINQ (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], outside LINQ
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
ms.openlocfilehash: 6ba6c6f50b4d2f717de4325b5cd21434066b2899
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43389189"
---
# <a name="how-to-use-lambda-expressions-outside-linq-c-programming-guide"></a><span data-ttu-id="3fa96-102">Cómo: Usar expresiones lambda fuera de LINQ (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3fa96-102">How to: Use Lambda Expressions Outside LINQ (C# Programming Guide)</span></span>
<span data-ttu-id="3fa96-103">Las expresiones lambda no están limitadas a las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fa96-103">Lambda expressions are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="3fa96-104">Se pueden usar en cualquier lugar en que se espere un valor de delegado, es decir, dondequiera que se puede usar un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="3fa96-104">You can use them anywhere a delegate value is expected, that is, wherever an anonymous method can be used.</span></span> <span data-ttu-id="3fa96-105">En el ejemplo siguiente se muestra cómo usar una expresión lambda en un controlador de eventos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3fa96-105">The following example shows how to use a lambda expression in a Windows Forms event handler.</span></span> <span data-ttu-id="3fa96-106">Observe que los tipos de las entradas (<xref:System.Object> y <xref:System.Windows.Forms.MouseEventArgs>) los deduce el compilador y no tienen que especificarse explícitamente en los parámetros de entrada lambda.</span><span class="sxs-lookup"><span data-stu-id="3fa96-106">Notice that the types of the inputs (<xref:System.Object> and <xref:System.Windows.Forms.MouseEventArgs>) are inferred by the compiler and do not have to be explicitly given in the lambda input parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa96-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fa96-107">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3fa96-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fa96-108">See Also</span></span>  
 [<span data-ttu-id="3fa96-109">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="3fa96-109">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [<span data-ttu-id="3fa96-110">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="3fa96-110">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [<span data-ttu-id="3fa96-111">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="3fa96-111">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
