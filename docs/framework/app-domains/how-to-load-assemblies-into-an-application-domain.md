---
title: Procedimiento para cargar ensamblados en un dominio de aplicación
description: Aprenda a cargar ensamblados en un dominio de aplicación en .NET. El método recomendado consiste en usar el método de carga estático (o compartido) de System.Reflection.Assembly.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
ms.openlocfilehash: cc37b5b5c64a65655d06418d08a66231577a5bad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271491"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="2b5df-104">Procedimiento para cargar ensamblados en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="2b5df-104">How to: Load Assemblies into an Application Domain</span></span>

<span data-ttu-id="2b5df-105">Existen numerosas formas de cargar un ensamblado en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2b5df-105">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="2b5df-106">El método recomendado consiste en usar el método <xref:System.Reflection.Assembly.Load%2A>`static` (`Shared` en Visual Basic) de la clase <xref:System.Reflection.Assembly?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b5df-106">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="2b5df-107">A continuación se indican otras formas de cargar los ensamblados:</span><span class="sxs-lookup"><span data-stu-id="2b5df-107">Other ways assemblies can be loaded include:</span></span>  
  
- <span data-ttu-id="2b5df-108">El método <xref:System.Reflection.Assembly.LoadFrom%2A> de la clase <xref:System.Reflection.Assembly> carga un ensamblado a partir de la ubicación del archivo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2b5df-108">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="2b5df-109">La carga de ensamblados mediante este método usa un contexto de carga distinto.</span><span class="sxs-lookup"><span data-stu-id="2b5df-109">Loading assemblies with this method uses a different load context.</span></span>  
  
- <span data-ttu-id="2b5df-110">Los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> y <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> cargan un ensamblado en el contexto de solo reflexión.</span><span class="sxs-lookup"><span data-stu-id="2b5df-110">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="2b5df-111">Los ensamblados cargados en este contexto pueden examinarse, pero no ejecutarse, lo que permite examinar los ensamblados que tienen como destino otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="2b5df-111">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="2b5df-112">Vea [Cómo: Cargar ensamblados en el contexto de solo reflexión](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="2b5df-112">See [How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b5df-113">El contexto de solo reflexión es nuevo en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2b5df-113">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
- <span data-ttu-id="2b5df-114">Los métodos como <xref:System.AppDomain.CreateInstance%2A> y <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> de la clase <xref:System.AppDomain> pueden cargar ensamblados en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2b5df-114">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
- <span data-ttu-id="2b5df-115">El método <xref:System.Type.GetType%2A> de la clase <xref:System.Type> puede cargar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2b5df-115">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
- <span data-ttu-id="2b5df-116">El método <xref:System.AppDomain.Load%2A> de la clase <xref:System.AppDomain?displayProperty=nameWithType> puede cargar ensamblados, pero se usa principalmente para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="2b5df-116">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=nameWithType> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="2b5df-117">No se debe usar para cargar ensamblados en un dominio de aplicación que no sea el dominio de aplicación desde el que se llama.</span><span class="sxs-lookup"><span data-stu-id="2b5df-117">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b5df-118">A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente.</span><span class="sxs-lookup"><span data-stu-id="2b5df-118">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="2b5df-119">Esto se aplica a la combinación de los componentes principal y secundario del número de versión.</span><span class="sxs-lookup"><span data-stu-id="2b5df-119">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="2b5df-120">Puede especificar cómo se comparte entre los dominios de aplicación el código compilado Just-In-Time (JIT) de los ensamblados cargados.</span><span class="sxs-lookup"><span data-stu-id="2b5df-120">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="2b5df-121">Para obtener más información, consulte [Dominios de aplicación y ensamblados](application-domains.md#application-domains-and-assemblies).</span><span class="sxs-lookup"><span data-stu-id="2b5df-121">For more information, see [Application domains and assemblies](application-domains.md#application-domains-and-assemblies).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b5df-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b5df-122">Example</span></span>  

 <span data-ttu-id="2b5df-123">El siguiente código carga un ensamblado llamado "example.exe" o "example.dll" en el dominio de aplicación actual, obtiene del ensamblado un tipo llamado `Example`, obtiene un método sin parámetros llamado `MethodA` para dicho tipo y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="2b5df-123">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="2b5df-124">Para obtener una descripción completa sobre cómo obtener información de un ensamblado cargado, consulte [Dynamically Loading and Using Types](../reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).</span><span class="sxs-lookup"><span data-stu-id="2b5df-124">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2b5df-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b5df-125">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [<span data-ttu-id="2b5df-126">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="2b5df-126">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="2b5df-127">Reflexión</span><span class="sxs-lookup"><span data-stu-id="2b5df-127">Reflection</span></span>](../reflection-and-codedom/reflection.md)
- [<span data-ttu-id="2b5df-128">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="2b5df-128">Using Application Domains</span></span>](use.md)
- [<span data-ttu-id="2b5df-129">Cómo: Cargar ensamblados en el contexto de solo reflexión</span><span class="sxs-lookup"><span data-stu-id="2b5df-129">How to: Load Assemblies into the Reflection-Only Context</span></span>](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)
- [<span data-ttu-id="2b5df-130">Dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="2b5df-130">Application domains and assemblies</span></span>](application-domains.md#application-domains-and-assemblies)
