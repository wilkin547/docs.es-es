---
description: 'Más información acerca de: Directiva de #Const'
title: '#Directiva Const'
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
ms.openlocfilehash: 9597666ee1320f5dfda226040f93a84eb60a3deb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797281"
---
# <a name="const-directive"></a><span data-ttu-id="ec44e-103">#Const (Directiva)</span><span class="sxs-lookup"><span data-stu-id="ec44e-103">#Const Directive</span></span>

<span data-ttu-id="ec44e-104">Define constantes de compilador condicionales para Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ec44e-104">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec44e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec44e-105">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ec44e-106">Partes</span><span class="sxs-lookup"><span data-stu-id="ec44e-106">Parts</span></span>  

 `constname`  
 <span data-ttu-id="ec44e-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ec44e-107">Required.</span></span> <span data-ttu-id="ec44e-108">Nombre de la constante que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="ec44e-108">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="ec44e-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ec44e-109">Required.</span></span> <span data-ttu-id="ec44e-110">Literal, otra constante del compilador condicional o cualquier combinación que incluya todos o todos los operadores aritméticos o lógicos, excepto `Is` .</span><span class="sxs-lookup"><span data-stu-id="ec44e-110">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec44e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec44e-111">Remarks</span></span>  

 <span data-ttu-id="ec44e-112">Las constantes de compilador condicionales siempre son privadas en el archivo en el que aparecen.</span><span class="sxs-lookup"><span data-stu-id="ec44e-112">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="ec44e-113">No se pueden crear constantes del compilador públicas mediante la `#Const` directiva; solo se pueden crear en la interfaz de usuario o con la `/define` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="ec44e-113">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="ec44e-114">Solo se pueden usar constantes y literales de compilador condicionales en `expression` .</span><span class="sxs-lookup"><span data-stu-id="ec44e-114">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="ec44e-115">El uso de una constante estándar definida con `Const` produce un error.</span><span class="sxs-lookup"><span data-stu-id="ec44e-115">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="ec44e-116">Por el contrario, puede usar constantes definidas con la `#Const` palabra clave solo para la compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="ec44e-116">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="ec44e-117">Las constantes también pueden ser undefined, en cuyo caso tienen un valor de `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="ec44e-117">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec44e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec44e-118">Example</span></span>  

 <span data-ttu-id="ec44e-119">En este ejemplo se usa la directiva `#Const`.</span><span class="sxs-lookup"><span data-stu-id="ec44e-119">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ec44e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec44e-120">See also</span></span>

- [<span data-ttu-id="ec44e-121">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec44e-121">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
- [<span data-ttu-id="ec44e-122">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="ec44e-122">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="ec44e-123">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="ec44e-123">Const Statement</span></span>](../statements/const-statement.md)
- [<span data-ttu-id="ec44e-124">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="ec44e-124">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="ec44e-125">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="ec44e-125">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
