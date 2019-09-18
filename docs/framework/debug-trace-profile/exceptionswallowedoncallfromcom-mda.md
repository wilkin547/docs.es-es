---
title: MDA de exceptionSwallowedOnCallFromCom
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a49bdce78c1445cd25de8755ded0f27a4902937
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052815"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="d69f4-102">MDA de exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="d69f4-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="d69f4-103">El asistente para la depuración administrada (MDA, por sus siglas en inglés) `exceptionSwallowedOnCallFromCOM` se activa cuando se produce una excepción del código de Common Language Runtime (CLR) llamado desde COM a través de un método que no tiene un tipo de resultado HRESULT sin administrar.</span><span class="sxs-lookup"><span data-stu-id="d69f4-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d69f4-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d69f4-104">Symptoms</span></span>  
 <span data-ttu-id="d69f4-105">Una llamada de COM a un componente administrado devuelve un valor FALSE o 0.</span><span class="sxs-lookup"><span data-stu-id="d69f4-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="d69f4-106">También puede ser que, si el método tiene un tipo de valor devuelto void, no haya indicación de que se produjese una excepción durante la ejecución del método.</span><span class="sxs-lookup"><span data-stu-id="d69f4-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="d69f4-107">En este caso, la excepción se detectará de forma silenciosa y la ejecución regresará al emisor de la llamada COM.</span><span class="sxs-lookup"><span data-stu-id="d69f4-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d69f4-108">Causa</span><span class="sxs-lookup"><span data-stu-id="d69f4-108">Cause</span></span>  
 <span data-ttu-id="d69f4-109">Se produjo una excepción, pero no hay ningún modo válido de notificarla.</span><span class="sxs-lookup"><span data-stu-id="d69f4-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d69f4-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="d69f4-110">Resolution</span></span>  
 <span data-ttu-id="d69f4-111">Solo tiene carácter informativo, no es necesariamente indicativo de un error.</span><span class="sxs-lookup"><span data-stu-id="d69f4-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d69f4-112">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="d69f4-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="d69f4-113">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="d69f4-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="d69f4-114">Solo recoge los datos sobre excepciones detectadas de forma silenciosa.</span><span class="sxs-lookup"><span data-stu-id="d69f4-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d69f4-115">Resultados</span><span class="sxs-lookup"><span data-stu-id="d69f4-115">Output</span></span>  
 <span data-ttu-id="d69f4-116">Mensaje informativo que contiene el nombre del método, el nombre del tipo y el mensaje de la excepción.</span><span class="sxs-lookup"><span data-stu-id="d69f4-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d69f4-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="d69f4-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d69f4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d69f4-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d69f4-119">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="d69f4-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d69f4-120">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d69f4-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
