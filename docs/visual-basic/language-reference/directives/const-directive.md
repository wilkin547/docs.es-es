---
title: '#<a name="const-directive"></a>#Const (directiva)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a><span data-ttu-id="db602-102">#Const (Directiva)</span><span class="sxs-lookup"><span data-stu-id="db602-102">#Const Directive</span></span>
<span data-ttu-id="db602-103">Permite definir constantes condicionales para el compilador de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="db602-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db602-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db602-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="db602-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="db602-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="db602-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db602-106">Required.</span></span> <span data-ttu-id="db602-107">Nombre de la constante que se está definida.</span><span class="sxs-lookup"><span data-stu-id="db602-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="db602-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db602-108">Required.</span></span> <span data-ttu-id="db602-109">Literal, otra constante de compilación condicional o cualquier combinación que incluya operadores aritméticos o lógicos, excepto `Is`.</span><span class="sxs-lookup"><span data-stu-id="db602-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db602-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db602-110">Remarks</span></span>  
 <span data-ttu-id="db602-111">Constantes de compilación condicional siempre son privados para el archivo en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="db602-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="db602-112">No se puede crear constantes de compilación públicas con el `#Const` directiva; puede crear solo en la interfaz de usuario o con el `/define` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="db602-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="db602-113">Puede usar únicamente constantes de compilación condicional y literales en `expression`.</span><span class="sxs-lookup"><span data-stu-id="db602-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="db602-114">Uso de una constante estándar definida con `Const` produce un error.</span><span class="sxs-lookup"><span data-stu-id="db602-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="db602-115">Por el contrario, puede usar constantes definidas con el `#Const` palabra clave solo para la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="db602-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="db602-116">Constantes también se definido, en cuyo caso tienen un valor de `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="db602-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db602-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db602-117">Example</span></span>  
 <span data-ttu-id="db602-118">En este ejemplo se usa la directiva `#Const`.</span><span class="sxs-lookup"><span data-stu-id="db602-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="db602-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="db602-119">See Also</span></span>  
 [<span data-ttu-id="db602-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db602-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="db602-121">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="db602-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="db602-122">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db602-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="db602-123">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="db602-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="db602-124">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db602-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
