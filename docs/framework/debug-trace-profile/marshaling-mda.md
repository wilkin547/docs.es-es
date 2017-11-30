---
title: "MDA de serialización"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f92e849798f03702ca9a5eab3120067a651c999
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="marshaling-mda"></a><span data-ttu-id="e9403-102">MDA de serialización</span><span class="sxs-lookup"><span data-stu-id="e9403-102">marshaling MDA</span></span>
<span data-ttu-id="e9403-103">El asistente para la depuración administrada (MDA) `marshaling` se activa cuando el CLR establece la información de cálculo de referencias para un parámetro de método o un campo de una estructura.</span><span class="sxs-lookup"><span data-stu-id="e9403-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="e9403-104">Este MDA no funciona para los ensamblados con compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="e9403-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e9403-105">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="e9403-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="e9403-106">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="e9403-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e9403-107">Resultado</span><span class="sxs-lookup"><span data-stu-id="e9403-107">Output</span></span>  
 <span data-ttu-id="e9403-108">El MDA muestra el tipo de parámetro o campo en los contextos administrados y no administrados, y la estructura o método que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="e9403-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="e9403-109">A continuación, se muestra un ejemplo de la salida de un campo:</span><span class="sxs-lookup"><span data-stu-id="e9403-109">The following is an example of the output for a field:</span></span>  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="e9403-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="e9403-110">Configuration</span></span>  
 <span data-ttu-id="e9403-111">La configuración de MDA permite filtrar la información de cálculo de referencias notificada sobre la base de los nombres de método o campo implicados.</span><span class="sxs-lookup"><span data-stu-id="e9403-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="e9403-112">En el ejemplo siguiente, se muestra el uso de los elementos `methodFilter`, `fieldFilter` y `match` para especificar filtros.</span><span class="sxs-lookup"><span data-stu-id="e9403-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="e9403-113">Al establecer el atributo `name` en un asterisco (*) coincidirá con todo.</span><span class="sxs-lookup"><span data-stu-id="e9403-113">Setting the `name` attribute to an asterisk (*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9403-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9403-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="e9403-115">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="e9403-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="e9403-116">Serialización para interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="e9403-116">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
