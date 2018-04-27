---
title: 'Cómo: Crear una nueva variable (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aff160584d3d1fe382020d5b8c25ac57dab66d92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="283e8-102">Cómo: Crear una nueva variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="283e8-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="283e8-103">Crear una variable con un [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="283e8-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="283e8-104">Para crear una nueva variable</span><span class="sxs-lookup"><span data-stu-id="283e8-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="283e8-105">Declare la variable en un `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="283e8-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="283e8-106">Incluyen especificaciones para las características de la variable, como [privada](../../../../visual-basic/language-reference/modifiers/private.md), [estático](../../../../visual-basic/language-reference/modifiers/static.md), [sombras](../../../../visual-basic/language-reference/modifiers/shadows.md), o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="283e8-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="283e8-107">Para obtener más información, consulte [características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="283e8-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="283e8-108">No es necesario el `Dim` palabra clave si utiliza otras palabras clave en la declaración.</span><span class="sxs-lookup"><span data-stu-id="283e8-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="283e8-109">Siga las especificaciones con el nombre de la variable, que debe seguir las convenciones y reglas de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="283e8-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="283e8-110">Para obtener más información, consulte [nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="283e8-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="283e8-111">Siga el nombre con el [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula para especificar el tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="283e8-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="283e8-112">Si no especifica el tipo de datos, utiliza el valor predeterminado: `Object`.</span><span class="sxs-lookup"><span data-stu-id="283e8-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="283e8-113">Siga el `As` cláusula con un signo igual (`=`) y siga el signo igual con el valor inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="283e8-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="283e8-114">Visual Basic asigna el valor especificado a la variable cada vez que se ejecuta el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="283e8-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="283e8-115">Si no especifica un valor inicial, Visual Basic asigna el valor inicial predeterminado para el tipo de datos de la variable cuando entra por primera vez el código que contiene el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="283e8-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="283e8-116">Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md) palabra clave en el `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="283e8-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="283e8-117">Si no usa `New`, el valor inicial de la variable es [nada](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="283e8-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="283e8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="283e8-118">See Also</span></span>  
 [<span data-ttu-id="283e8-119">Variables</span><span class="sxs-lookup"><span data-stu-id="283e8-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="283e8-120">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="283e8-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="283e8-121">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="283e8-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="283e8-122">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="283e8-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="283e8-123">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="283e8-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="283e8-124">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="283e8-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="283e8-125">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="283e8-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="283e8-126">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="283e8-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
