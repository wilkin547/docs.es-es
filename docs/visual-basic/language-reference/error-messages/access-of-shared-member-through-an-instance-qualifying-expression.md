---
title: Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 773a97c301e7cb5bec0234ae466d487ec9716437
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250346"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="e4c67-102">Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará</span><span class="sxs-lookup"><span data-stu-id="e4c67-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>

<span data-ttu-id="e4c67-103">Una variable de instancia de una clase o estructura se utiliza para tener acceso a una variable, una propiedad, un procedimiento o un evento `Shared` definidos en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e4c67-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="e4c67-104">Esta advertencia también puede producirse si se usa una variable de instancia para tener acceso a un miembro compartido implícitamente de una clase o estructura, como una constante o una enumeración, o una clase o estructura anidada.</span><span class="sxs-lookup"><span data-stu-id="e4c67-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>

<span data-ttu-id="e4c67-105">El propósito de compartir un miembro es crear una sola copia de ese miembro y hacer que esa copia única esté disponible para cada instancia de la clase o estructura en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="e4c67-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="e4c67-106">Es coherente con este propósito para tener acceso a un miembro `Shared` a través del nombre de su clase o estructura, en lugar de una variable que contiene una instancia individual de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e4c67-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>

<span data-ttu-id="e4c67-107">El acceso a un miembro `Shared` a través de una variable de instancia puede hacer que el código sea más difícil de entender si se oculta el hecho de que el miembro es `Shared`.</span><span class="sxs-lookup"><span data-stu-id="e4c67-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="e4c67-108">Además, si dicho acceso forma parte de una expresión que realiza otras acciones, como un procedimiento `Function` que devuelve una instancia del miembro compartido, Visual Basic omite la expresión y cualquier otra acción que, de lo contrario, realizaría.</span><span class="sxs-lookup"><span data-stu-id="e4c67-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
<span data-ttu-id="e4c67-109">Para obtener más información y un ejemplo, vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e4c67-109">For more information and an example, see [Shared](../modifiers/shared.md).</span></span>  
  
<span data-ttu-id="e4c67-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e4c67-110">By default, this message is a warning.</span></span> <span data-ttu-id="e4c67-111">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e4c67-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
<span data-ttu-id="e4c67-112">**IDENTIFICADOR de error:** BC42025</span><span class="sxs-lookup"><span data-stu-id="e4c67-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4c67-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e4c67-113">To correct this error</span></span>  
  
<span data-ttu-id="e4c67-114">Use el nombre de la clase o estructura que define el miembro `Shared` para tener acceso a él, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4c67-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example:</span></span>
  
```vb
Public Class TestClass
    Public Shared Sub SayHello()
        MsgBox("Hello")
    End Sub
End Class
  
Module Program
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New TestClass()
        tc.SayHello()
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        TestClass.SayHello()
    End Sub  
End Module  
```  
  
> [!NOTE]
> <span data-ttu-id="e4c67-115">Debe alertar sobre los efectos del ámbito cuando dos elementos de programación tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="e4c67-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="e4c67-116">En el ejemplo anterior, si declara una instancia de mediante `Dim testClass as testClass = Nothing`, el compilador trata una llamada a `testClass.sayHello()` como un acceso al método a través del nombre de la clase y no se produce ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="e4c67-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e4c67-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4c67-117">See also</span></span>

- [<span data-ttu-id="e4c67-118">Shared</span><span class="sxs-lookup"><span data-stu-id="e4c67-118">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="e4c67-119">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4c67-119">Scope in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/scope.md)
