---
title: MDA de invalidMemberDeclaration
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 6033cd4178b2bc493794b5dcc527bc543ba24284
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216298"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="b906c-102">MDA de invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="b906c-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="b906c-103">El asistente para la depuración administrada (MDA) de `invalidMemberDeclaration` se activa para informar acerca de un error que se produce a la hora de determinar cómo serializar los parámetros de un miembro al que se va a llamar desde COM.</span><span class="sxs-lookup"><span data-stu-id="b906c-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b906c-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="b906c-104">Symptoms</span></span>  
 <span data-ttu-id="b906c-105">Se devuelve a COM un valor HRESULT de error sin que se haya llamado al método administrado.</span><span class="sxs-lookup"><span data-stu-id="b906c-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b906c-106">Causa</span><span class="sxs-lookup"><span data-stu-id="b906c-106">Cause</span></span>  
 <span data-ttu-id="b906c-107">Esto probablemente se debe a un atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatible en uno de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="b906c-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b906c-108">Solución</span><span class="sxs-lookup"><span data-stu-id="b906c-108">Resolution</span></span>  
 <span data-ttu-id="b906c-109">Especifique los atributos <xref:System.Runtime.InteropServices.MarshalAsAttribute> válidos en los parámetros.</span><span class="sxs-lookup"><span data-stu-id="b906c-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b906c-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="b906c-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="b906c-111">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="b906c-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b906c-112">Output</span><span class="sxs-lookup"><span data-stu-id="b906c-112">Output</span></span>  
 <span data-ttu-id="b906c-113">Mensaje informativo que contiene el nombre de miembro, el nombre de tipo y el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b906c-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b906c-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="b906c-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b906c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b906c-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b906c-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="b906c-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b906c-117">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="b906c-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
