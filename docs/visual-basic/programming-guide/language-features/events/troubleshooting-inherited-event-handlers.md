---
title: Solucionar problemas de controladores de eventos heredados en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: f6355cf7fc2e43651c1112d048220a8179968c76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646338"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="295ca-102">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="295ca-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="295ca-103">Este tema enumeran los problemas comunes que surgen con controladores de eventos en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="295ca-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="295ca-104">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="295ca-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="295ca-105">Código de controlador de eventos se ejecuta dos veces por cada llamada</span><span class="sxs-lookup"><span data-stu-id="295ca-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="295ca-106">Un controlador de eventos heredado no debe incluir un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="295ca-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="295ca-107">El método de la clase base ya está asociado con el evento y se activará en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="295ca-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="295ca-108">Quitar el `Handles` cláusula del método heredado.</span><span class="sxs-lookup"><span data-stu-id="295ca-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="295ca-109">Si el método heredado no tiene una `Handles` (palabra clave), compruebe que el código no contiene un archivo extra [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlen el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="295ca-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295ca-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="295ca-110">See Also</span></span>  
 [<span data-ttu-id="295ca-111">Eventos</span><span class="sxs-lookup"><span data-stu-id="295ca-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
