---
title: Solucionar problemas de controladores de eventos heredados en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e8f0b669566bbee6530931bfba9808fad0c085
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="d9bcd-102">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9bcd-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="d9bcd-103">Este tema enumeran los problemas comunes que surgen con controladores de eventos en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="d9bcd-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d9bcd-104">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d9bcd-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="d9bcd-105">Código de controlador de eventos se ejecuta dos veces por cada llamada</span><span class="sxs-lookup"><span data-stu-id="d9bcd-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="d9bcd-106">Un controlador de eventos heredado no debe incluir un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="d9bcd-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="d9bcd-107">El método de la clase base ya está asociado con el evento y se activará en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="d9bcd-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="d9bcd-108">Quitar el `Handles` cláusula del método heredado.</span><span class="sxs-lookup"><span data-stu-id="d9bcd-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="d9bcd-109">Si el método heredado no tiene una `Handles` (palabra clave), compruebe que el código no contiene un archivo extra [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlen el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="d9bcd-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9bcd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9bcd-110">See Also</span></span>  
 [<span data-ttu-id="d9bcd-111">Eventos</span><span class="sxs-lookup"><span data-stu-id="d9bcd-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
