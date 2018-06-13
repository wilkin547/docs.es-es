---
title: 'Cómo: Cargar ensamblados en un dominio de aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0925f7445c4451f61bd1c878cc66300d62bdc855
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741911"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="0754b-102">Cómo: Cargar ensamblados en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="0754b-102">How to: Load Assemblies into an Application Domain</span></span>
<span data-ttu-id="0754b-103">Existen numerosas formas de cargar un ensamblado en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0754b-103">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="0754b-104">El método recomendado consiste en usar el método <xref:System.Reflection.Assembly.Load%2A> `static` (`Shared` en Visual Basic) de la clase <xref:System.Reflection.Assembly?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0754b-104">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="0754b-105">A continuación se indican otras formas de cargar los ensamblados:</span><span class="sxs-lookup"><span data-stu-id="0754b-105">Other ways assemblies can be loaded include:</span></span>  
  
-   <span data-ttu-id="0754b-106">El método <xref:System.Reflection.Assembly.LoadFrom%2A> de la clase <xref:System.Reflection.Assembly> carga un ensamblado a partir de la ubicación del archivo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0754b-106">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="0754b-107">La carga de ensamblados mediante este método usa un contexto de carga distinto.</span><span class="sxs-lookup"><span data-stu-id="0754b-107">Loading assemblies with this method uses a different load context.</span></span>  
  
-   <span data-ttu-id="0754b-108">Los métodos <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> y <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> cargan un ensamblado en el contexto de solo reflexión.</span><span class="sxs-lookup"><span data-stu-id="0754b-108">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="0754b-109">Los ensamblados cargados en este contexto pueden examinarse, pero no ejecutarse, lo que permite examinar los ensamblados que tienen como destino otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="0754b-109">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="0754b-110">Consulte [Cómo: Cargar ensamblados en el contexto de solo reflexión](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="0754b-110">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0754b-111">El contexto de solo reflexión es nuevo en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0754b-111">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
-   <span data-ttu-id="0754b-112">Los métodos como <xref:System.AppDomain.CreateInstance%2A> y <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> de la clase <xref:System.AppDomain> pueden cargar ensamblados en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0754b-112">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
-   <span data-ttu-id="0754b-113">El método <xref:System.Type.GetType%2A> de la clase <xref:System.Type> puede cargar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0754b-113">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
-   <span data-ttu-id="0754b-114">El método <xref:System.AppDomain.Load%2A> de la clase <xref:System.AppDomain?displayProperty=nameWithType> puede cargar ensamblados, pero se usa principalmente para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="0754b-114">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=nameWithType> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="0754b-115">No se debe usar para cargar ensamblados en un dominio de aplicación que no sea el dominio de aplicación desde el que se llama.</span><span class="sxs-lookup"><span data-stu-id="0754b-115">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0754b-116">A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente.</span><span class="sxs-lookup"><span data-stu-id="0754b-116">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="0754b-117">Esto se aplica a la combinación de los componentes principal y secundario del número de versión.</span><span class="sxs-lookup"><span data-stu-id="0754b-117">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="0754b-118">Puede especificar cómo se comparte entre los dominios de aplicación el código compilado Just-In-Time (JIT) de los ensamblados cargados.</span><span class="sxs-lookup"><span data-stu-id="0754b-118">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="0754b-119">Para obtener más información, consulte [Dominios de aplicación y ensamblados](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346).</span><span class="sxs-lookup"><span data-stu-id="0754b-119">For more information, see [Application Domains and Assemblies](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0754b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0754b-120">Example</span></span>  
 <span data-ttu-id="0754b-121">El siguiente código carga un ensamblado llamado "example.exe" o "example.dll" en el dominio de aplicación actual, obtiene del ensamblado un tipo llamado `Example`, obtiene un método sin parámetros llamado `MethodA` para dicho tipo y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0754b-121">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="0754b-122">Para obtener una descripción completa sobre cómo obtener información de un ensamblado cargado, consulte [Dynamically Loading and Using Types](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md) (Cargar y usar tipos dinámicamente).</span><span class="sxs-lookup"><span data-stu-id="0754b-122">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0754b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0754b-123">See Also</span></span>  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>  
 [<span data-ttu-id="0754b-124">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="0754b-124">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)  
 [<span data-ttu-id="0754b-125">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0754b-125">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 [<span data-ttu-id="0754b-126">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="0754b-126">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 [<span data-ttu-id="0754b-127">Cargar ensamblados en el contexto de solo reflexión</span><span class="sxs-lookup"><span data-stu-id="0754b-127">How to: Load Assemblies into the Reflection-Only Context</span></span>](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)  
 [<span data-ttu-id="0754b-128">Dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="0754b-128">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)
