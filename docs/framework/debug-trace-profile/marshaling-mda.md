---
title: MDA de serialización
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 463c8e42e76a61eb0820c1af72c20d004161ad25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184475"
---
# <a name="marshaling-mda"></a><span data-ttu-id="cc9a9-102">MDA de serialización</span><span class="sxs-lookup"><span data-stu-id="cc9a9-102">marshaling MDA</span></span>
<span data-ttu-id="cc9a9-103">El asistente para la depuración administrada (MDA) `marshaling` se activa cuando el CLR establece la información de cálculo de referencias para un parámetro de método o un campo de una estructura.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="cc9a9-104">Este MDA no funciona para los ensamblados con compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cc9a9-105">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="cc9a9-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="cc9a9-106">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cc9a9-107">Salida</span><span class="sxs-lookup"><span data-stu-id="cc9a9-107">Output</span></span>  
 <span data-ttu-id="cc9a9-108">El MDA muestra el tipo de parámetro o campo en los contextos administrados y no administrados, y la estructura o método que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="cc9a9-109">A continuación, se muestra un ejemplo de la salida de un campo:</span><span class="sxs-lookup"><span data-stu-id="cc9a9-109">The following is an example of the output for a field:</span></span>  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="cc9a9-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="cc9a9-110">Configuration</span></span>  
 <span data-ttu-id="cc9a9-111">La configuración de MDA permite filtrar la información de serialización notificada sobre la base de los nombres de método o campo implicados.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="cc9a9-112">En el ejemplo siguiente, se muestra el uso de los elementos `methodFilter`, `fieldFilter` y `match` para especificar filtros.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="cc9a9-113">Al establecer el atributo `name` en un asterisco (\*) coincidirá con todo.</span><span class="sxs-lookup"><span data-stu-id="cc9a9-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cc9a9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc9a9-114">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="cc9a9-115">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="cc9a9-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="cc9a9-116">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="cc9a9-116">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
