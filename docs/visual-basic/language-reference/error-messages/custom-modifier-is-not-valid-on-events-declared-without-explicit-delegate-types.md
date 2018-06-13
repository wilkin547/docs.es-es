---
title: '&#39;Personalizado&#39; modificador no es válido en eventos declarados sin tipos de delegado explícitos'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587529"
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="a13a3-102">&#39;Personalizado&#39; modificador no es válido en eventos declarados sin tipos de delegado explícitos</span><span class="sxs-lookup"><span data-stu-id="a13a3-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="a13a3-103">A diferencia de un evento no personalizado, un `Custom Event` declaración requiere un `As` cláusula después el nombre del evento que especifica explícitamente el tipo de delegado para el evento.</span><span class="sxs-lookup"><span data-stu-id="a13a3-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="a13a3-104">Eventos personalizados no se pueden definir con un `As` cláusula y explícito tipo de delegado, o con un parámetro de lista inmediatamente después del nombre de evento.</span><span class="sxs-lookup"><span data-stu-id="a13a3-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="a13a3-105">**Id. de error:** BC31122</span><span class="sxs-lookup"><span data-stu-id="a13a3-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a13a3-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a13a3-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="a13a3-107">Defina a un delegado con la misma lista de parámetros que el evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="a13a3-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="a13a3-108">Por ejemplo, si la `Custom Event` definieron de forma `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, a continuación, el delegado correspondiente sería la siguiente.</span><span class="sxs-lookup"><span data-stu-id="a13a3-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="a13a3-109">Reemplazar la lista de parámetros del evento personalizado con un `As` cláusula que especifica el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="a13a3-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="a13a3-110">Siguiendo con el ejemplo, `Custom Event` sería reescrita declaración como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="a13a3-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="a13a3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a13a3-111">Example</span></span>  
 <span data-ttu-id="a13a3-112">Este ejemplo se declara un `Custom Event` y especifica los necesarios `As` cláusula con un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="a13a3-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a13a3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a13a3-113">See Also</span></span>  
 [<span data-ttu-id="a13a3-114">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a13a3-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="a13a3-115">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a13a3-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="a13a3-116">Eventos</span><span class="sxs-lookup"><span data-stu-id="a13a3-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
