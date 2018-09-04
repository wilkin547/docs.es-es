---
title: 'Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 8f85ba0adea522851e45b20ef5024491874c9a29
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564533"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="c8171-102">Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8171-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="c8171-103">Puede desasociar una variable de objeto de cualquier instancia de objeto si se establece en [nada](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="c8171-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="c8171-104">Para desasociar una variable de objeto de cualquier instancia de objeto</span><span class="sxs-lookup"><span data-stu-id="c8171-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="c8171-105">Establezca la variable en `Nothing` en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="c8171-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="c8171-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c8171-106">Robust Programming</span></span>  
 <span data-ttu-id="c8171-107">Si el código intenta tener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing`, un <xref:System.NullReferenceException> se produce.</span><span class="sxs-lookup"><span data-stu-id="c8171-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="c8171-108">Si establece una variable de objeto en `Nothing` con frecuencia, o si es posible que la variable no se ha inicializado, es una buena idea incluir accesos de miembros en un `Try...Catch...Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="c8171-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c8171-109">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8171-109">.NET Framework Security</span></span>  
 <span data-ttu-id="c8171-110">Si usa una variable de objeto para objetos que contienen datos confidenciales, puede establecer la variable `Nothing` cuando no activamente trabaja con uno de esos objetos.</span><span class="sxs-lookup"><span data-stu-id="c8171-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="c8171-111">Esto reduce la posibilidad de programas malintencionados obtengan acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="c8171-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8171-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8171-112">See Also</span></span>  
 <xref:System.NullReferenceException>  
 [<span data-ttu-id="c8171-113">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="c8171-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="c8171-114">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="c8171-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="c8171-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="c8171-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="c8171-116">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c8171-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="c8171-117">Solución de problemas de excepciones: System.NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="c8171-117">Troubleshooting Exceptions: System.NullReferenceException</span></span>](https://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
