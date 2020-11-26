---
title: MDA de exceptionSwallowedOnCallFromCom
description: Revise el Asistente para la depuración administrada de exceptionSwallowedOnCallFromCOM en .NET. Este MDA se produce si se produce una excepción, pero no hay ninguna manera adecuada de notificarla.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 11daccb4d1e757bf2fae25858d706eee5921c509
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244358"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="23943-104">MDA de exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="23943-104">exceptionSwallowedOnCallFromCom MDA</span></span>

<span data-ttu-id="23943-105">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `exceptionSwallowedOnCallFromCOM` se activa cuando se produce una excepción del código de Common Language Runtime (CLR) llamado desde COM a través de un método que no tiene un tipo de resultado HRESULT sin administrar.</span><span class="sxs-lookup"><span data-stu-id="23943-105">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="23943-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="23943-106">Symptoms</span></span>  

 <span data-ttu-id="23943-107">Una llamada de COM a un componente administrado devuelve un valor FALSE o 0.</span><span class="sxs-lookup"><span data-stu-id="23943-107">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="23943-108">También puede ser que, si el método tiene un tipo de valor devuelto void, no haya indicación de que se produjese una excepción durante la ejecución del método.</span><span class="sxs-lookup"><span data-stu-id="23943-108">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="23943-109">En este caso, la excepción se detectará de forma silenciosa y la ejecución regresará al emisor de la llamada COM.</span><span class="sxs-lookup"><span data-stu-id="23943-109">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="23943-110">Causa</span><span class="sxs-lookup"><span data-stu-id="23943-110">Cause</span></span>  

 <span data-ttu-id="23943-111">Se produjo una excepción, pero no hay ningún modo válido de notificarla.</span><span class="sxs-lookup"><span data-stu-id="23943-111">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="23943-112">Solución</span><span class="sxs-lookup"><span data-stu-id="23943-112">Resolution</span></span>  

 <span data-ttu-id="23943-113">Solo tiene carácter informativo, no es necesariamente indicativo de un error.</span><span class="sxs-lookup"><span data-stu-id="23943-113">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="23943-114">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="23943-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="23943-115">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="23943-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="23943-116">Solo recoge los datos sobre excepciones detectadas de forma silenciosa.</span><span class="sxs-lookup"><span data-stu-id="23943-116">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="23943-117">Resultados</span><span class="sxs-lookup"><span data-stu-id="23943-117">Output</span></span>  

 <span data-ttu-id="23943-118">Mensaje informativo que contiene el nombre del método, el nombre del tipo y el mensaje de la excepción.</span><span class="sxs-lookup"><span data-stu-id="23943-118">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="23943-119">Configuración</span><span class="sxs-lookup"><span data-stu-id="23943-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="23943-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="23943-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="23943-121">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="23943-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="23943-122">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="23943-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
