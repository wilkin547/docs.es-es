---
title: MDA de loadFromContext
description: Entender el Asistente para la depuración administrada (MDA) de loadFromContext en .NET, que se activa si se carga un ensamblado en el contexto LoadFrom.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: 631939b38ace4d26d0deb5b104cc5de0df3d9f3a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247361"
---
# <a name="loadfromcontext-mda"></a><span data-ttu-id="9314b-103">MDA de loadFromContext</span><span class="sxs-lookup"><span data-stu-id="9314b-103">loadFromContext MDA</span></span>

<span data-ttu-id="9314b-104">El asistente para la depuración administrada (MDA) `loadFromContext` se activa si se carga un ensamblado en el contexto de `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="9314b-104">The `loadFromContext` managed debugging assistant (MDA) is activated if an assembly is loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="9314b-105">Esta situación puede producirse como resultado de llamar a <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> u otros métodos similares.</span><span class="sxs-lookup"><span data-stu-id="9314b-105">This situation can occur as a result of calling <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or other similar methods.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9314b-106">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9314b-106">Symptoms</span></span>  

 <span data-ttu-id="9314b-107">El uso de algunos métodos de cargador puede dar lugar a ensamblados que se carguen en el contexto de `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="9314b-107">The use of some loader methods can result in assemblies being loaded in the `LoadFrom` context.</span></span> <span data-ttu-id="9314b-108">El uso de este contexto puede provocar un comportamiento inesperado para la serialización, conversión y resolución de dependencias.</span><span class="sxs-lookup"><span data-stu-id="9314b-108">The use of this context can result in unexpected behavior for serialization, casting, and dependency resolution.</span></span> <span data-ttu-id="9314b-109">Por lo general, se recomienda que los ensamblados se carguen en el contexto de `Load` para evitar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="9314b-109">In general, it is recommended that assemblies be loaded into the `Load` context to avoid these problems.</span></span> <span data-ttu-id="9314b-110">Sin este MDA es difícil determinar en qué contexto se ha cargado un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9314b-110">It is difficult to determine which context an assembly has been loaded into without this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9314b-111">Causa</span><span class="sxs-lookup"><span data-stu-id="9314b-111">Cause</span></span>  

 <span data-ttu-id="9314b-112">Por lo general, un ensamblado se carga en el contexto de `LoadFrom` si se cargó desde una ruta de acceso fuera del contexto de `Load`, como la caché global de ensamblados o la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9314b-112">Generally, an assembly was loaded into the `LoadFrom` context if it was loaded from a path outside the `Load` context, such as the global assembly cache or the <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9314b-113">Solución</span><span class="sxs-lookup"><span data-stu-id="9314b-113">Resolution</span></span>  

 <span data-ttu-id="9314b-114">Configure las aplicaciones para que las llamadas a <xref:System.Reflection.Assembly.LoadFrom%2A> ya no sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="9314b-114">Configure applications such that <xref:System.Reflection.Assembly.LoadFrom%2A> calls are no longer needed.</span></span> <span data-ttu-id="9314b-115">Puede usar las técnicas siguientes para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="9314b-115">You can use the following techniques for doing so:</span></span>  
  
- <span data-ttu-id="9314b-116">Instalar ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9314b-116">Install assemblies in the global assembly cache.</span></span>  
  
- <span data-ttu-id="9314b-117">Coloque los ensamblados en el directorio <xref:System.AppDomainSetup.ApplicationBase%2A> del <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9314b-117">Place assemblies in the <xref:System.AppDomainSetup.ApplicationBase%2A> directory for the <xref:System.AppDomain>.</span></span> <span data-ttu-id="9314b-118">En el caso del dominio predeterminado, el directorio <xref:System.AppDomainSetup.ApplicationBase%2A> es el que contiene el archivo ejecutable que inició el proceso.</span><span class="sxs-lookup"><span data-stu-id="9314b-118">In the case of the default domain, the <xref:System.AppDomainSetup.ApplicationBase%2A> directory is the one that contains the executable file that started the process.</span></span> <span data-ttu-id="9314b-119">Es posible que esto también requiera crear un <xref:System.AppDomain> si no es conveniente mover el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9314b-119">This might also require creating a new <xref:System.AppDomain> if it is not convenient to move the assembly.</span></span>  
  
- <span data-ttu-id="9314b-120">Agregue una ruta de acceso de sondeo al archivo de configuración (.config) de la aplicación o a dominios de aplicación secundarios si los ensamblados dependientes se encuentran en directorios secundarios en relación con el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9314b-120">Add a probing path to your application configuration (.config) file or to secondary  application domains if dependent assemblies are in child directories relative to the executable.</span></span>  
  
 <span data-ttu-id="9314b-121">En cada caso, se puede cambiar el código para usar el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9314b-121">In each case, the code can be changed to use the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9314b-122">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="9314b-122">Effect on the Runtime</span></span>  

 <span data-ttu-id="9314b-123">El MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="9314b-123">The MDA does not have any effect on the CLR.</span></span> <span data-ttu-id="9314b-124">Informa del contexto que se usó como resultado de una solicitud de carga.</span><span class="sxs-lookup"><span data-stu-id="9314b-124">It reports the context that was used as a result of a load request.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9314b-125">Resultados</span><span class="sxs-lookup"><span data-stu-id="9314b-125">Output</span></span>  

 <span data-ttu-id="9314b-126">El MDA informa de que el ensamblado se cargó en el contexto de `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="9314b-126">The MDA reports that the assembly was loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="9314b-127">Especifica el nombre simple del ensamblado y la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9314b-127">It specifies the simple name of the assembly and the path.</span></span> <span data-ttu-id="9314b-128">También sugiere mitigaciones para evitar el uso del contexto de `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="9314b-128">It also suggests mitigations to avoid using the `LoadFrom` context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9314b-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="9314b-129">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="9314b-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9314b-130">Example</span></span>  

 <span data-ttu-id="9314b-131">En el ejemplo de código siguiente se muestra una situación que puede activar este MDA:</span><span class="sxs-lookup"><span data-stu-id="9314b-131">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is
            // located outside of the Load context probing path.
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9314b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9314b-132">See also</span></span>

- [<span data-ttu-id="9314b-133">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="9314b-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
