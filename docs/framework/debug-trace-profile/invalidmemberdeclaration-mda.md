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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e5b4cb4a04a79a748f4ea2292bac67a88a6e9f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131292"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="aadda-102">MDA de invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="aadda-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="aadda-103">El asistente para la depuración administrada (MDA) de `invalidMemberDeclaration` se activa para informar acerca de un error que se produce a la hora de determinar cómo serializar los parámetros de un miembro al que se va a llamar desde COM.</span><span class="sxs-lookup"><span data-stu-id="aadda-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="aadda-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="aadda-104">Symptoms</span></span>  
 <span data-ttu-id="aadda-105">Se devuelve a COM un valor HRESULT de error sin que se haya llamado al método administrado.</span><span class="sxs-lookup"><span data-stu-id="aadda-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="aadda-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="aadda-106">Cause</span></span>  
 <span data-ttu-id="aadda-107">Esto probablemente se debe a un atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatible en uno de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="aadda-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="aadda-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="aadda-108">Resolution</span></span>  
 <span data-ttu-id="aadda-109">Especifique los atributos <xref:System.Runtime.InteropServices.MarshalAsAttribute> válidos en los parámetros.</span><span class="sxs-lookup"><span data-stu-id="aadda-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="aadda-110">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="aadda-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="aadda-111">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="aadda-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="aadda-112">Salida</span><span class="sxs-lookup"><span data-stu-id="aadda-112">Output</span></span>  
 <span data-ttu-id="aadda-113">Mensaje informativo que contiene el nombre de miembro, el nombre de tipo y el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="aadda-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="aadda-114">Configuración</span><span class="sxs-lookup"><span data-stu-id="aadda-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aadda-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="aadda-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="aadda-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="aadda-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="aadda-117">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="aadda-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
