---
title: 'Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 320dadb61c12f3339c5328dcef31c41503892c56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352894"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="5c56b-102">Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c56b-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="5c56b-103">Puede desasociar una variable de objeto de cualquier instancia de objeto estableciéndolo en [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="5c56b-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="5c56b-104">Para desasociar una variable de objeto de cualquier instancia de objeto</span><span class="sxs-lookup"><span data-stu-id="5c56b-104">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="5c56b-105">Establezca la variable en `Nothing` en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="5c56b-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="5c56b-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="5c56b-106">Robust Programming</span></span>  
 <span data-ttu-id="5c56b-107">Si el código intenta tener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing`, se produce una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="5c56b-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="5c56b-108">Si establece una variable de objeto en `Nothing` con frecuencia, o si es posible, la variable no se inicializa, es aconsejable incluir los accesos de los miembros en un bloque de `Try...Catch...Finally`.</span><span class="sxs-lookup"><span data-stu-id="5c56b-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5c56b-109">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5c56b-109">.NET Framework Security</span></span>  
 <span data-ttu-id="5c56b-110">Si usa una variable de objeto para los objetos que contienen datos confidenciales o confidenciales, puede establecer la variable en `Nothing` cuando no esté tratando activamente con uno de esos objetos.</span><span class="sxs-lookup"><span data-stu-id="5c56b-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="5c56b-111">Esto reduce la posibilidad de que el código malintencionado obtenga acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="5c56b-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c56b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c56b-112">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="5c56b-113">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="5c56b-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="5c56b-114">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="5c56b-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="5c56b-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="5c56b-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="5c56b-116">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5c56b-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
