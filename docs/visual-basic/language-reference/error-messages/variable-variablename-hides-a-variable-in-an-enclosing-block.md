---
title: "Variable &#39; &lt;variablename&gt;&#39; oculta una variable en un bloque de inclusión"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords: BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2af570cd002b4be4e15a7c03b0ffc2ff84ba3982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="e64e8-102">Variable &#39; &lt;variablename&gt;&#39; oculta una variable en un bloque de inclusión</span><span class="sxs-lookup"><span data-stu-id="e64e8-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="e64e8-103">Una variable incluida en un bloque tiene el mismo nombre que otra variable local.</span><span class="sxs-lookup"><span data-stu-id="e64e8-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="e64e8-104">**Id. de error:** BC30616</span><span class="sxs-lookup"><span data-stu-id="e64e8-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e64e8-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e64e8-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e64e8-106">Cambiar el nombre de la variable del bloque contenedor para que no sea igual que cualquier otra variable local.</span><span class="sxs-lookup"><span data-stu-id="e64e8-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="e64e8-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e64e8-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="e64e8-108">Una causa común de este error es el uso de `Catch e As Exception` dentro de un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="e64e8-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="e64e8-109">Si este es el caso, el nombre del `Catch` variable de bloque `ex` en lugar de `e`.</span><span class="sxs-lookup"><span data-stu-id="e64e8-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="e64e8-110">Otra fuente común de este error es un intento para tener acceso a una variable local declarada dentro de un `Try` bloquear en otro `Catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="e64e8-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="e64e8-111">Para corregir este error, declare la variable fuera de la `Try...Catch...Finally` estructura.</span><span class="sxs-lookup"><span data-stu-id="e64e8-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e64e8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e64e8-112">See Also</span></span>  
 [<span data-ttu-id="e64e8-113">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e64e8-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="e64e8-114">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="e64e8-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
