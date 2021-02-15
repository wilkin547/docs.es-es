---
description: 'Más información sobre: Cómo: hacer que una variable de objeto no haga referencia a ninguna instancia (Visual Basic)'
title: Procedimiento para crear una variable de objeto que no haga referencia a ninguna instancia
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 2897720b52e708847fdd139be512e578a7420241
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481875"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="6a312-103">Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a312-103">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>

<span data-ttu-id="6a312-104">Puede desasociar una variable de objeto de cualquier instancia de objeto estableciéndolo en [Nothing](../../../language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="6a312-104">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="6a312-105">Para desasociar una variable de objeto de cualquier instancia de objeto</span><span class="sxs-lookup"><span data-stu-id="6a312-105">To disassociate an object variable from any object instance</span></span>  
  
- <span data-ttu-id="6a312-106">Establezca la variable `Nothing` en en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="6a312-106">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="6a312-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="6a312-107">Robust Programming</span></span>  

 <span data-ttu-id="6a312-108">Si el código intenta obtener acceso a un miembro de una variable de objeto que se ha establecido en `Nothing` , <xref:System.NullReferenceException> se produce una.</span><span class="sxs-lookup"><span data-stu-id="6a312-108">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="6a312-109">Si establece una variable de objeto con `Nothing` frecuencia, o si es posible, la variable no se inicializa, es aconsejable incluir los accesos de los miembros en un `Try...Catch...Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="6a312-109">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6a312-110">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a312-110">.NET Framework Security</span></span>  

 <span data-ttu-id="6a312-111">Si usa una variable de objeto para los objetos que contienen datos confidenciales o confidenciales, puede establecer la variable en `Nothing` cuando no esté tratando activamente con uno de esos objetos.</span><span class="sxs-lookup"><span data-stu-id="6a312-111">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="6a312-112">Esto reduce la posibilidad de que el código malintencionado obtenga acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="6a312-112">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a312-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a312-113">See also</span></span>

- <xref:System.NullReferenceException>
- [<span data-ttu-id="6a312-114">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="6a312-114">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="6a312-115">Asignación de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="6a312-115">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="6a312-116">Nothing</span><span class="sxs-lookup"><span data-stu-id="6a312-116">Nothing</span></span>](../../../language-reference/nothing.md)
- [<span data-ttu-id="6a312-117">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6a312-117">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
