---
title: MDA de memberInfoCacheCreation
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3b65ecc226c1caf7b53d746f0583e1f57c7d8c1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052465"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="a175a-102">MDA de memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="a175a-102">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="a175a-103">El asistente para la depuración administrada (MDA) `memberInfoCacheCreation` se activa cuando se crea una caché de <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="a175a-103">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="a175a-104">Esto es una indicación clara de un programa que está usando características de reflexión que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="a175a-104">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a175a-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="a175a-105">Symptoms</span></span>  
 <span data-ttu-id="a175a-106">El espacio de trabajo de un programa aumenta porque el programa está usando reflexión que consume muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="a175a-106">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a175a-107">Causa</span><span class="sxs-lookup"><span data-stu-id="a175a-107">Cause</span></span>  
 <span data-ttu-id="a175a-108">Las operaciones de reflexión que implican dos objetos <xref:System.Reflection.MemberInfo> se consideran que consumen muchos recursos porque deben leer metadatos que se almacenan en páginas frías y en general indican que el programa usa algún tipo de escenario enlazado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a175a-108">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a175a-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="a175a-109">Resolution</span></span>  
 <span data-ttu-id="a175a-110">Puede determinar dónde se usa la reflexión en su programa si habilita este MDA y, después, ejecuta el código en un depurador o lo adjunta con un depurador cuando se activa el MDA.</span><span class="sxs-lookup"><span data-stu-id="a175a-110">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="a175a-111">Bajo un depurador obtendrá un seguimiento de pila en el que se muestra dónde se creó la caché de <xref:System.Reflection.MemberInfo> y desde allí puede determinar dónde usa la reflexión el programa.</span><span class="sxs-lookup"><span data-stu-id="a175a-111">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="a175a-112">La resolución depende de los objetivos del código.</span><span class="sxs-lookup"><span data-stu-id="a175a-112">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="a175a-113">Este MDA le avisa de que el programa tiene un escenario enlazado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a175a-113">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="a175a-114">Es posible que quiera determinar si puede sustituir un escenario enlazado en tiempo de compilación o considerar el rendimiento del escenario enlazado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a175a-114">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a175a-115">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="a175a-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="a175a-116">Este MDA se activa para cada caché de <xref:System.Reflection.MemberInfo> que se crea.</span><span class="sxs-lookup"><span data-stu-id="a175a-116">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="a175a-117">El rendimiento se ve afectado de forma insignificante.</span><span class="sxs-lookup"><span data-stu-id="a175a-117">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a175a-118">Resultados</span><span class="sxs-lookup"><span data-stu-id="a175a-118">Output</span></span>  
 <span data-ttu-id="a175a-119">El MDA genera un mensaje que indica que se creó la caché de <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="a175a-119">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="a175a-120">Use un depurador para realizar un seguimiento de pila en el que se muestre dónde usa la reflexión el programa.</span><span class="sxs-lookup"><span data-stu-id="a175a-120">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a175a-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="a175a-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="a175a-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a175a-122">Example</span></span>  
 <span data-ttu-id="a175a-123">Este código de ejemplo activará el MDA `memberInfoCacheCreation`.</span><span class="sxs-lookup"><span data-stu-id="a175a-123">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a175a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a175a-124">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="a175a-125">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="a175a-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
