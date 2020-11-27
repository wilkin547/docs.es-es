---
title: MDA de serialización
description: Revise el Asistente para la depuración administrada (MDA) de serialización, que se invoca si CLR configura la información de cálculo de referencias para un parámetro de método o un campo de estructura.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: afe54a2104e05f8fad57c7cbba4988b013aff761
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271179"
---
# <a name="marshaling-mda"></a><span data-ttu-id="379bc-103">MDA de serialización</span><span class="sxs-lookup"><span data-stu-id="379bc-103">marshaling MDA</span></span>

<span data-ttu-id="379bc-104">El asistente para la depuración administrada (MDA) `marshaling` se activa cuando el CLR establece la información de cálculo de referencias para un parámetro de método o un campo de una estructura.</span><span class="sxs-lookup"><span data-stu-id="379bc-104">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="379bc-105">Este MDA no funciona para los ensamblados con compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="379bc-105">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="379bc-106">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="379bc-106">Effect on the Runtime</span></span>  

 <span data-ttu-id="379bc-107">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="379bc-107">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="379bc-108">Resultados</span><span class="sxs-lookup"><span data-stu-id="379bc-108">Output</span></span>  

 <span data-ttu-id="379bc-109">El MDA muestra el tipo de parámetro o campo en los contextos administrados y no administrados, y la estructura o método que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="379bc-109">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="379bc-110">A continuación, se muestra un ejemplo de la salida de un campo:</span><span class="sxs-lookup"><span data-stu-id="379bc-110">The following is an example of the output for a field:</span></span>  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="379bc-111">Configuración</span><span class="sxs-lookup"><span data-stu-id="379bc-111">Configuration</span></span>  

 <span data-ttu-id="379bc-112">La configuración de MDA permite filtrar la información de serialización notificada sobre la base de los nombres de método o campo implicados.</span><span class="sxs-lookup"><span data-stu-id="379bc-112">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="379bc-113">En el ejemplo siguiente, se muestra el uso de los elementos `methodFilter`, `fieldFilter` y `match` para especificar filtros.</span><span class="sxs-lookup"><span data-stu-id="379bc-113">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="379bc-114">Establecer el `name` atributo en un asterisco ( \* ) coincidirá con todo.</span><span class="sxs-lookup"><span data-stu-id="379bc-114">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="379bc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="379bc-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="379bc-116">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="379bc-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="379bc-117">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="379bc-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
