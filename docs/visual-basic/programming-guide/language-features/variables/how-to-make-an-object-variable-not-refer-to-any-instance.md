---
title: Procedimiento Crea un objeto de Variable no hacen referencia a cualquier instancia (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 820d4cb9d17bf467d257bfbba5f43f07228c0b4f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663553"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="da9c3-102">Procedimiento Crea un objeto de Variable no hacen referencia a cualquier instancia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da9c3-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="da9c3-103">Puede desasociar una variable de objeto de cualquier instancia de objeto si se establece en [nada](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="da9c3-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="da9c3-104">Para desasociar una variable de objeto de cualquier instancia de objeto</span><span class="sxs-lookup"><span data-stu-id="da9c3-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="da9c3-105">Establezca la variable en `Nothing` en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="da9c3-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="da9c3-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="da9c3-106">Robust Programming</span></span>  
 <span data-ttu-id="da9c3-107">Si el código intenta tener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing`, un <xref:System.NullReferenceException> se produce.</span><span class="sxs-lookup"><span data-stu-id="da9c3-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="da9c3-108">Si establece una variable de objeto en `Nothing` con frecuencia, o si es posible que la variable no se ha inicializado, es una buena idea incluir accesos de miembros en un `Try...Catch...Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="da9c3-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="da9c3-109">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da9c3-109">.NET Framework Security</span></span>  
 <span data-ttu-id="da9c3-110">Si usa una variable de objeto para objetos que contienen datos confidenciales, puede establecer la variable `Nothing` cuando no activamente trabaja con uno de esos objetos.</span><span class="sxs-lookup"><span data-stu-id="da9c3-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="da9c3-111">Esto reduce la posibilidad de programas malintencionados obtengan acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="da9c3-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9c3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="da9c3-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="da9c3-113">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="da9c3-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="da9c3-114">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="da9c3-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="da9c3-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="da9c3-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="da9c3-116">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="da9c3-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
