---
title: "Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords: BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bcf3c37852e73464eec612e9e1d458ca707342e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="4c6af-102">Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará</span><span class="sxs-lookup"><span data-stu-id="4c6af-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="4c6af-103">Se utiliza una variable de instancia de una clase o estructura para tener acceso a un `Shared` variable, propiedad, procedimiento o evento definido en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4c6af-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="4c6af-104">Esta advertencia también puede producirse si una variable de instancia se utiliza para tener acceso a un miembro implícitamente compartido de una clase o estructura, como una constante o enumeración, o una clase anidada o una estructura.</span><span class="sxs-lookup"><span data-stu-id="4c6af-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="4c6af-105">El propósito de compartir a un miembro es crear una sola copia de ese miembro y que esa sola copia esté disponible para todas las instancias de la clase o estructura en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="4c6af-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="4c6af-106">Es coherente con este fin para tener acceso a un `Shared` miembro mediante el nombre de su clase o estructura, y no a través de una variable que contiene una instancia individual de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="4c6af-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="4c6af-107">Obtener acceso a un `Shared` miembro a través de una variable de instancia puede hacer más difícil de entender ocultando el hecho de que el miembro es el código `Shared`.</span><span class="sxs-lookup"><span data-stu-id="4c6af-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="4c6af-108">Además, si el acceso forma parte de una expresión que lleva a cabo otras acciones, como un `Function` procedimiento que devuelve una instancia del miembro compartido, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] omite la expresión y todas las demás acciones que realizaría en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="4c6af-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="4c6af-109">Para obtener más información y un ejemplo, vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4c6af-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="4c6af-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="4c6af-110">By default, this message is a warning.</span></span> <span data-ttu-id="4c6af-111">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4c6af-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4c6af-112">**Id. de error:** BC42025</span><span class="sxs-lookup"><span data-stu-id="4c6af-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c6af-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4c6af-113">To correct this error</span></span>  
  
-   <span data-ttu-id="4c6af-114">Utilice el nombre de la clase o estructura que define el `Shared` miembro que se va a obtener acceso a él, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c6af-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="4c6af-115">Aparecer la alerta para los efectos de ámbito cuando dos elementos de programación tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="4c6af-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="4c6af-116">En el ejemplo anterior, si se declara una instancia mediante el uso de `Dim testClass as testClass = Nothing`, el compilador trata una llamada a `testClass.sayHello()` tal y como se produce el acceso del método por el nombre de clase y ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="4c6af-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6af-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c6af-117">See Also</span></span>  
 [<span data-ttu-id="4c6af-118">Shared</span><span class="sxs-lookup"><span data-stu-id="4c6af-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="4c6af-119">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c6af-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
