---
title: 'Ejemplo: solucionar problemas de programación dinámica'
ms.date: 03/30/2017
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
ms.openlocfilehash: 0cff232668b9eb65b09a22b14e4ae58673ccd6d0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288078"
---
# <a name="example-troubleshooting-dynamic-programming"></a><span data-ttu-id="f1cce-102">Ejemplo: solucionar problemas de programación dinámica</span><span class="sxs-lookup"><span data-stu-id="f1cce-102">Example: Troubleshooting Dynamic Programming</span></span>

> [!NOTE]
> <span data-ttu-id="f1cce-103">En este tema se hace referencia a .NET Native Developer Preview, que es una versión preliminar del software.</span><span class="sxs-lookup"><span data-stu-id="f1cce-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="f1cce-104">Puede descargar esta versión preliminar desde el [sitio web de Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (es necesario registrarse).</span><span class="sxs-lookup"><span data-stu-id="f1cce-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="f1cce-105">No todos los errores de búsqueda de metadatos en las aplicaciones desarrolladas con la cadena de herramientas de .NET Native producen una excepción.</span><span class="sxs-lookup"><span data-stu-id="f1cce-105">Not all metadata lookup failures in apps developed using the .NET Native tool chain result in an exception.</span></span>  <span data-ttu-id="f1cce-106">Algunos pueden manifestarse de manera impredecible en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1cce-106">Some can manifest in unpredictable ways in an app.</span></span>  <span data-ttu-id="f1cce-107">En el ejemplo siguiente se muestra una infracción de acceso causada por hacer referencia a un objeto nulo:</span><span class="sxs-lookup"><span data-stu-id="f1cce-107">The following example shows an access violation caused by referencing a null object:</span></span>  
  
```output
Access violation - code c0000005 (first chance)  
App!$3_App::Core::Util::NavigationArgs.Setup  
App!$3_App::Core::Util::NavigationArgs..ctor  
App!$0_App::Gibbon::Util::DesktopNavigationArgs..ctor  
App!$0_App::ViewModels::DesktopAppVM.NavigateToPage  
App!$3_App::Core::ViewModels::AppViewModel.NavigateToFirstPage  
App!$3_App::Core::ViewModels::AppViewModel::<HandleLaunch>d__a.MoveNext  
App!$43_System::Runtime::CompilerServices::AsyncMethodBuilderCore.CallMoveNext  
App!System::Action.InvokeClosedStaticThunk  
App!System::Action.Invoke  
App!$43_System::Threading::Tasks::AwaitTaskContinuation.InvokeAction  
App!$43_System::Threading::SendOrPostCallback.InvokeOpenStaticThunk  
[snip]  
```  
  
 <span data-ttu-id="f1cce-108">Vamos a intentar solucionar esta excepción mediante el enfoque de tres pasos descrito en la sección "Resolver manualmente los metadatos que faltan" de [Introducción](getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="f1cce-108">Let's try to troubleshoot this exception by using the three-step approach outlined in the "Manually resolve missing metadata" section of [Getting Started](getting-started-with-net-native.md).</span></span>  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="f1cce-109">¿Qué estaba haciendo la aplicación?</span><span class="sxs-lookup"><span data-stu-id="f1cce-109">What was the app doing?</span></span>  

 <span data-ttu-id="f1cce-110">Lo primero que hay tener en cuenta es la maquinaria de la palabra clave `async` en la base de la pila.</span><span class="sxs-lookup"><span data-stu-id="f1cce-110">The first thing to note is the `async` keyword machinery at the base of the stack.</span></span>  <span data-ttu-id="f1cce-111">Determinar lo que la aplicación estaba haciendo realmente en un método `async` puede ser problemático, ya que la pila ha perdido el contexto de la llamada original y ha ejecutado el código `async` en un subproceso diferente.</span><span class="sxs-lookup"><span data-stu-id="f1cce-111">Determining what the app was really doing in an `async` method can be problematic, because the stack has lost the context of the originating call and has run the `async` code on a different thread.</span></span> <span data-ttu-id="f1cce-112">Sin embargo, podemos deducir que la aplicación estaba intentando cargar su primera página.</span><span class="sxs-lookup"><span data-stu-id="f1cce-112">However, we can deduce that the app is trying to load its first page.</span></span>  <span data-ttu-id="f1cce-113">En la implementación de `NavigationArgs.Setup`, el código siguiente produjo la infracción de acceso:</span><span class="sxs-lookup"><span data-stu-id="f1cce-113">In the implementation for `NavigationArgs.Setup`, the following code caused the access violation:</span></span>  
  
`AppViewModel.Current.LayoutVM.PageMap`  
  
 <span data-ttu-id="f1cce-114">En esta instancia, la propiedad `LayoutVM` en `AppViewModel.Current` era **NULL**.</span><span class="sxs-lookup"><span data-stu-id="f1cce-114">In this instance, the `LayoutVM` property on `AppViewModel.Current` was **null**.</span></span>  <span data-ttu-id="f1cce-115">Alguna ausencia de metadatos provocó una diferencia de comportamiento que provocó que una propiedad tuviese un estado no inicializado en vez de establecido, como esperaba la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1cce-115">Some absence of metadata caused a subtle behavior difference and resulted in a property being uninitialized instead of set, as the app expected.</span></span>  <span data-ttu-id="f1cce-116">Establecer un punto de interrupción en el código donde `LayoutVM` debería haberse inicializado podría arrojar luz sobre la situación.</span><span class="sxs-lookup"><span data-stu-id="f1cce-116">Setting a breakpoint in the code where `LayoutVM` should have been initialized might throw light on the situation.</span></span>  <span data-ttu-id="f1cce-117">Sin embargo, tenga en cuenta que el tipo de `LayoutVM` es `App.Core.ViewModels.Layout.LayoutApplicationVM`.</span><span class="sxs-lookup"><span data-stu-id="f1cce-117">However, note that `LayoutVM`’s type is `App.Core.ViewModels.Layout.LayoutApplicationVM`.</span></span>  <span data-ttu-id="f1cce-118">La única directiva de metadatos presente en el archivo rd.xml es:</span><span class="sxs-lookup"><span data-stu-id="f1cce-118">The only metadata directive present so far in the rd.xml file is:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
```  
  
 <span data-ttu-id="f1cce-119">Una causa probable del error es que a `App.Core.ViewModels.Layout.LayoutApplicationVM` le falten metadatos porque está en un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="f1cce-119">A likely candidate for the failure is that `App.Core.ViewModels.Layout.LayoutApplicationVM` is missing metadata because it's in a different namespace.</span></span>  
  
 <span data-ttu-id="f1cce-120">En este caso, agregar una directiva de tiempo de ejecución para `App.Core.ViewModels` ha resuelto el problema.</span><span class="sxs-lookup"><span data-stu-id="f1cce-120">In this case, adding a runtime directive for `App.Core.ViewModels` resolved the issue.</span></span> <span data-ttu-id="f1cce-121">La causa principal ha sido una llamada de la API al método <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> que ha devuelto **NULL**, y la aplicación ha omitido el problema de forma silenciosa hasta que se ha producido un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f1cce-121">The root cause was an API call to the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method that returned **null**, and the app silently ignored the problem until a crash occurred.</span></span>  
  
 <span data-ttu-id="f1cce-122">En la programación dinámica, una buena práctica al usar las API de reflexión en .NET Native es usar las <xref:System.Type.GetType%2A?displayProperty=nameWithType> sobrecargas que producen una excepción en caso de error.</span><span class="sxs-lookup"><span data-stu-id="f1cce-122">In dynamic programming, a good practice when using reflection APIs under .NET Native is to use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> overloads that throw an exception on failure.</span></span>  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="f1cce-123">¿Es un caso aislado?</span><span class="sxs-lookup"><span data-stu-id="f1cce-123">Is this an isolated case?</span></span>  

 <span data-ttu-id="f1cce-124">También pueden surgir otros problemas al utilizar `App.Core.ViewModels`.</span><span class="sxs-lookup"><span data-stu-id="f1cce-124">Other issues might also arise when using `App.Core.ViewModels`.</span></span>  <span data-ttu-id="f1cce-125">Debe decidir si merece la pena identificar y corregir cada excepción debida a la falta de metadatos, o ahorrar tiempo y agregar directivas para una clase más grande de tipos.</span><span class="sxs-lookup"><span data-stu-id="f1cce-125">You must decide whether it’s worth identifying and fixing each missing metadata exception, or saving time and adding directives for a larger class of types.</span></span>  <span data-ttu-id="f1cce-126">Aquí, agregar metadatos `dynamic` para `App.Core.ViewModels` podría ser el mejor método si el aumento de tamaño resultante del archivo binario de salida no supone un problema.</span><span class="sxs-lookup"><span data-stu-id="f1cce-126">Here, adding `dynamic` metadata for `App.Core.ViewModels` might be the best approach if the resulting size increase of the output binary isn’t an issue.</span></span>  
  
## <a name="could-the-code-be-rewritten"></a><span data-ttu-id="f1cce-127">¿Podría modificarse el código?</span><span class="sxs-lookup"><span data-stu-id="f1cce-127">Could the code be rewritten?</span></span>  

 <span data-ttu-id="f1cce-128">Si la aplicación hubiera usado `typeof(LayoutApplicationVM)` en lugar de `Type.GetType("LayoutApplicationVM")`, la cadena de herramientas podría haber conservado los metadatos de `browse`.</span><span class="sxs-lookup"><span data-stu-id="f1cce-128">If the app had used `typeof(LayoutApplicationVM)` instead of `Type.GetType("LayoutApplicationVM")`, the tool chain could have preserved `browse` metadata.</span></span>  <span data-ttu-id="f1cce-129">En cambio, aun así no habría creado metadatos de `invoke`, que habrían producido una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md) al crear una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="f1cce-129">However, it still wouldn't have created `invoke` metadata, which would have led to a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception when instantiating the type.</span></span> <span data-ttu-id="f1cce-130">Para evitar la excepción, se tendría que agregar una directiva de tiempo de ejecución para el espacio de nombres o el tipo que especifica la directiva `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="f1cce-130">To prevent the exception, you'd still have to add a runtime directive for the namespace or the type that specifies the `dynamic` policy.</span></span> <span data-ttu-id="f1cce-131">Para obtener información sobre las directivas de tiempo de ejecución, vea [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f1cce-131">For information on runtime directives, see the [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cce-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1cce-132">See also</span></span>

- [<span data-ttu-id="f1cce-133">Introducción</span><span class="sxs-lookup"><span data-stu-id="f1cce-133">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="f1cce-134">Ejemplo: control de excepciones al enlazar datos</span><span class="sxs-lookup"><span data-stu-id="f1cce-134">Example: Handling Exceptions When Binding Data</span></span>](example-handling-exceptions-when-binding-data.md)
