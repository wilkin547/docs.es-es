---
title: El tipo de la variable '<variablename>' no se inferirá porque está enlazado a un campo en un ámbito de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: a595f38f6dd68b9c152bfa78ec0bebf36e173e17
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649968"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="0f73d-102">El tipo de variable '\<NombreDeVariable >' no se inferirá porque está enlazado a un campo en un ámbito de inclusión</span><span class="sxs-lookup"><span data-stu-id="0f73d-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="0f73d-103">El tipo de variable '\<NombreDeVariable >' no se inferirá porque está enlazado a un campo en un ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="0f73d-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="0f73d-104">Cambie el nombre de '\<NombreDeVariable >', o utilice el nombre completo (por ejemplo, 'Me.nombreDeVariable' o 'MiBase.nombreDeVariable').</span><span class="sxs-lookup"><span data-stu-id="0f73d-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="0f73d-105">Una variable de control de bucle en su código tiene el mismo nombre que un campo de la clase u otro ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="0f73d-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="0f73d-106">Dado que la variable de control se utiliza sin una cláusula `As`, se enlaza al campo en el ámbito de inclusión y el compilador no crea una nueva variable para ella ni infiere su tipo.</span><span class="sxs-lookup"><span data-stu-id="0f73d-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="0f73d-107">En el ejemplo siguiente, `Index`, es decir, la variable de control en la instrucción `For`, se enlaza al campo `Index` de la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="0f73d-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="0f73d-108">El compilador no crea una nueva variable para la variable de control `Index` ni infiere su tipo.</span><span class="sxs-lookup"><span data-stu-id="0f73d-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
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
  
 <span data-ttu-id="0f73d-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="0f73d-109">By default, this message is a warning.</span></span> <span data-ttu-id="0f73d-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0f73d-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0f73d-111">**Identificador de error:** BC42110</span><span class="sxs-lookup"><span data-stu-id="0f73d-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="0f73d-112">Para resolver esta advertencia</span><span class="sxs-lookup"><span data-stu-id="0f73d-112">To address this warning</span></span>  
  
- <span data-ttu-id="0f73d-113">Convierta la variable de control de bucle en local cambiando su nombre por un identificador que tampoco sea el nombre de un campo de la clase.</span><span class="sxs-lookup"><span data-stu-id="0f73d-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
- <span data-ttu-id="0f73d-114">Asegúrese de que la variable de control de bucle se enlaza al campo de clase agregando el prefijo `Me.` al nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="0f73d-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
- <span data-ttu-id="0f73d-115">En lugar de basarse en la inferencia de tipo local, use una cláusula `As` para especificar un tipo para la variable de control de bucle.</span><span class="sxs-lookup"><span data-stu-id="0f73d-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="0f73d-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f73d-116">Example</span></span>  
 <span data-ttu-id="0f73d-117">El código siguiente muestra el ejemplo anterior con la primera corrección en contexto.</span><span class="sxs-lookup"><span data-stu-id="0f73d-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f73d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f73d-118">See also</span></span>

- [<span data-ttu-id="0f73d-119">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0f73d-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="0f73d-120">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0f73d-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="0f73d-121">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0f73d-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="0f73d-122">Cómo: Hacer referencia a la instancia actual de un objeto</span><span class="sxs-lookup"><span data-stu-id="0f73d-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="0f73d-123">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="0f73d-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="0f73d-124">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="0f73d-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
