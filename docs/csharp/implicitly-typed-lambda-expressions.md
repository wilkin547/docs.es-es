---
title: Expresiones lambda con tipo implícito
description: Obtenga información sobre por qué no puede usar una declaración de variable con tipo implícito para declarar una expresión lambda.
ms.date: 06/20/2016
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: 0a6b52ba49ea39c0cb37e72b0ad40e18986c9be0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517672"
---
# <a name="implicitly-typed-lambda-expressions"></a><span data-ttu-id="f8471-103">Expresiones lambda con tipo implícito</span><span class="sxs-lookup"><span data-stu-id="f8471-103">Implicitly typed lambda expressions</span></span>

<span data-ttu-id="f8471-104">No estoy usando `var` para declarar este árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="f8471-104">I'm not using `var` to declare this expression tree.</span></span> <span data-ttu-id="f8471-105">No puede usar una declaración de variable con tipo implícito para declarar una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="f8471-105">You can't use an implicitly typed variable declaration to declare a lambda expression.</span></span>
<span data-ttu-id="f8471-106">Crea un problema de lógica circular para el compilador.</span><span class="sxs-lookup"><span data-stu-id="f8471-106">It creates a circular logic problem for the compiler.</span></span> <span data-ttu-id="f8471-107">La declaración `var` indica al compilador que detecte el tipo de variable del tipo de expresión en el lado derecho del operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="f8471-107">The `var` declaration tells the compiler to figure out the type of the variable from the type of expression on the right hand side of the assignment operator.</span></span> <span data-ttu-id="f8471-108">Una expresión lambda no tiene un tipo de tiempo de compilación, pero puede convertirse en cualquier tipo de expresión o delegado coincidente.</span><span class="sxs-lookup"><span data-stu-id="f8471-108">A lambda expression does not have a compile time type, but is convertible to any matching delegate or expression type.</span></span> <span data-ttu-id="f8471-109">Cuando asigna una expresión lambda a una variable de un tipo de expresión o delegado, indica al compilador que pruebe y convierta la expresión lambda en una expresión o delegado que coincida con la firma de la variable "assigned to".</span><span class="sxs-lookup"><span data-stu-id="f8471-109">When you assign a lambda expression to a variable of a delegate or expression type, you tell the compiler to try and convert the lambda expression into an expression or delegate that matches the signature of the 'assigned to' variable.</span></span> <span data-ttu-id="f8471-110">El compilador debe intentar que lo que se encuentra en el lado derecho de la asignación coincida con el tipo del lado izquierdo de la asignación.</span><span class="sxs-lookup"><span data-stu-id="f8471-110">The compiler must try to make the thing on the right hand side of the assignment match the type on the left hand side of the assignment.</span></span> 

<span data-ttu-id="f8471-111">Ambos lados de la asignación no pueden indicar al compilador que se dirija al objeto del otro lado del operador de asignación y vea si coincide con el tipo.</span><span class="sxs-lookup"><span data-stu-id="f8471-111">Both sides of the assignment can't be telling the compiler to look at the object on the other side of the assignment operator and see if my type matches.</span></span>

<span data-ttu-id="f8471-112">Puede obtener más información sobre por qué el lenguaje de C# especifica ese comportamiento con la lectura de [este artículo](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (descarga de PDF).</span><span class="sxs-lookup"><span data-stu-id="f8471-112">You can get even more details on why the C# language specifies that behavior by reading [this article](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (PDF Download)</span></span>


