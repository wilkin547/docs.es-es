---
description: Más información acerca de cómo solucionar problemas de controladores de eventos heredados en Visual Basic
title: Solución de problemas de controladores de eventos heredados
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: b489b6c85510bb942b403a508b6bbe232c3e1853
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424481"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="66913-103">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66913-103">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>

<span data-ttu-id="66913-104">En este tema se enumeran los problemas comunes que surgen con los controladores de eventos en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="66913-104">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="66913-105">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="66913-105">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="66913-106">El código del controlador de eventos se ejecuta dos veces para cada llamada</span><span class="sxs-lookup"><span data-stu-id="66913-106">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="66913-107">Un controlador de eventos heredado no debe incluir una cláusula [Handles](../../../language-reference/statements/handles-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="66913-107">An inherited event handler must not include a [Handles](../../../language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="66913-108">El método de la clase base ya está asociado al evento y se activará en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="66913-108">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="66913-109">Quite la `Handles` cláusula del método heredado.</span><span class="sxs-lookup"><span data-stu-id="66913-109">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="66913-110">Si el método heredado no tiene una `Handles` palabra clave, compruebe que el código no contiene una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) adicional o cualquier otro método que controle el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="66913-110">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66913-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="66913-111">See also</span></span>

- [<span data-ttu-id="66913-112">Eventos</span><span class="sxs-lookup"><span data-stu-id="66913-112">Events</span></span>](index.md)
