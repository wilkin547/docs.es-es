---
title: MDA de invalidMemberDeclaration
description: Revise el Asistente para la depuración administrada invalidMemberDeclaration, que se invoca si se devuelve un valor HRESULT de error a COM sin llamar al método administrado.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051719"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="17461-103">MDA de invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="17461-103">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="17461-104">El asistente para la depuración administrada (MDA) de `invalidMemberDeclaration` se activa para informar acerca de un error que se produce a la hora de determinar cómo serializar los parámetros de un miembro al que se va a llamar desde COM.</span><span class="sxs-lookup"><span data-stu-id="17461-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="17461-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="17461-105">Symptoms</span></span>  
 <span data-ttu-id="17461-106">Se devuelve a COM un valor HRESULT de error sin que se haya llamado al método administrado.</span><span class="sxs-lookup"><span data-stu-id="17461-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="17461-107">Causa</span><span class="sxs-lookup"><span data-stu-id="17461-107">Cause</span></span>  
 <span data-ttu-id="17461-108">Esto probablemente se debe a un atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatible en uno de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="17461-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="17461-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="17461-109">Resolution</span></span>  
 <span data-ttu-id="17461-110">Especifique los atributos <xref:System.Runtime.InteropServices.MarshalAsAttribute> válidos en los parámetros.</span><span class="sxs-lookup"><span data-stu-id="17461-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="17461-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="17461-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="17461-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="17461-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="17461-113">Output</span><span class="sxs-lookup"><span data-stu-id="17461-113">Output</span></span>  
 <span data-ttu-id="17461-114">Mensaje informativo que contiene el nombre de miembro, el nombre de tipo y el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="17461-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="17461-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="17461-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17461-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="17461-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="17461-117">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="17461-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="17461-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="17461-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
