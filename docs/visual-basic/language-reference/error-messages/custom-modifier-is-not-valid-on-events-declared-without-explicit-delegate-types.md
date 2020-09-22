---
title: El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 88cdeccd7a3411b57a77116bde64d0a2cf8e537d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874533"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="55ac3-102">El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos</span><span class="sxs-lookup"><span data-stu-id="55ac3-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>

<span data-ttu-id="55ac3-103">A diferencia de un evento no personalizado, una `Custom Event` declaración requiere una `As` cláusula que siga el nombre del evento que especifica explícitamente el tipo de delegado para el evento.</span><span class="sxs-lookup"><span data-stu-id="55ac3-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="55ac3-104">Los eventos no personalizados se pueden definir con una `As` cláusula y un tipo de delegado explícito, o con una lista de parámetros inmediatamente después del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="55ac3-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="55ac3-105">**Identificador de error:** BC31122</span><span class="sxs-lookup"><span data-stu-id="55ac3-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="55ac3-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="55ac3-106">To correct this error</span></span>  
  
1. <span data-ttu-id="55ac3-107">Defina un delegado con la misma lista de parámetros que el evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="55ac3-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="55ac3-108">Por ejemplo, si `Custom Event` se definió mediante `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , el delegado correspondiente sería el siguiente.</span><span class="sxs-lookup"><span data-stu-id="55ac3-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="55ac3-109">Reemplace la lista de parámetros del evento personalizado por una `As` cláusula que especifique el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="55ac3-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="55ac3-110">Siguiendo con el ejemplo, la `Custom Event` declaración se volvería a escribir de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="55ac3-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="55ac3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55ac3-111">Example</span></span>  

 <span data-ttu-id="55ac3-112">Este ejemplo declara `Custom Event` y especifica la `As` cláusula necesaria con un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="55ac3-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="55ac3-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55ac3-113">See also</span></span>

- [<span data-ttu-id="55ac3-114">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="55ac3-114">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="55ac3-115">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="55ac3-115">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="55ac3-116">Eventos</span><span class="sxs-lookup"><span data-stu-id="55ac3-116">Events</span></span>](../../programming-guide/language-features/events/index.md)
