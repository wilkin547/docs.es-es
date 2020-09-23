---
title: Solución de problemas de controladores de eventos heredados
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: d228e916e45054bc088aa633afd9d591e592210d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058006"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="b9135-102">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9135-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>

<span data-ttu-id="b9135-103">En este tema se enumeran los problemas comunes que surgen con los controladores de eventos en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="b9135-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b9135-104">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="b9135-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="b9135-105">El código del controlador de eventos se ejecuta dos veces para cada llamada</span><span class="sxs-lookup"><span data-stu-id="b9135-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="b9135-106">Un controlador de eventos heredado no debe incluir una cláusula [Handles](../../../language-reference/statements/handles-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="b9135-106">An inherited event handler must not include a [Handles](../../../language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="b9135-107">El método de la clase base ya está asociado al evento y se activará en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b9135-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="b9135-108">Quite la `Handles` cláusula del método heredado.</span><span class="sxs-lookup"><span data-stu-id="b9135-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="b9135-109">Si el método heredado no tiene una `Handles` palabra clave, compruebe que el código no contiene una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) adicional o cualquier otro método que controle el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="b9135-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9135-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9135-110">See also</span></span>

- [<span data-ttu-id="b9135-111">Eventos</span><span class="sxs-lookup"><span data-stu-id="b9135-111">Events</span></span>](index.md)
