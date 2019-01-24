---
title: '##Const (directiva) (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 7e855f76a0fa8e6c06fd557a944c518641415f09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710604"
---
# <a name="const-directive"></a><span data-ttu-id="77350-102">#Const (Directiva)</span><span class="sxs-lookup"><span data-stu-id="77350-102">#Const Directive</span></span>
<span data-ttu-id="77350-103">Define las constantes de compilador condicionales para Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77350-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77350-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77350-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="77350-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="77350-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="77350-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="77350-106">Required.</span></span> <span data-ttu-id="77350-107">Nombre de la constante que se está definida.</span><span class="sxs-lookup"><span data-stu-id="77350-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="77350-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="77350-108">Required.</span></span> <span data-ttu-id="77350-109">Literal, otra constante de compilación condicional o cualquier combinación que incluya operadores aritméticos o lógicos, excepto `Is`.</span><span class="sxs-lookup"><span data-stu-id="77350-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77350-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77350-110">Remarks</span></span>  
 <span data-ttu-id="77350-111">Constantes de compilador condicionales son siempre privadas en el archivo en el que aparecen.</span><span class="sxs-lookup"><span data-stu-id="77350-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="77350-112">No se puede crear constantes de compilación público con el `#Const` directiva; puede crear solo en la interfaz de usuario o con el `/define` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="77350-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="77350-113">Puede usar solo constantes de compilador condicionales y literales en `expression`.</span><span class="sxs-lookup"><span data-stu-id="77350-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="77350-114">Uso de una constante estándar definida con `Const` produce un error.</span><span class="sxs-lookup"><span data-stu-id="77350-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="77350-115">Por el contrario, puede usar constantes definidas con el `#Const` palabra clave para la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="77350-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="77350-116">Las constantes pueden también no estén definidas, en cuyo caso su valor `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="77350-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77350-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77350-117">Example</span></span>  
 <span data-ttu-id="77350-118">En este ejemplo se usa la directiva `#Const`.</span><span class="sxs-lookup"><span data-stu-id="77350-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="77350-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="77350-119">See also</span></span>
- [<span data-ttu-id="77350-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77350-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="77350-121">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="77350-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="77350-122">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="77350-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="77350-123">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="77350-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="77350-124">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="77350-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
