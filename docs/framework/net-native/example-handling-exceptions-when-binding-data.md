---
title: 'Ejemplo: control de excepciones al enlazar datos'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
ms.openlocfilehash: 399bd1af9ef25eca9cdfe1e13fdc4c01021babcd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251079"
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="c7fd4-102">Ejemplo: control de excepciones al enlazar datos</span><span class="sxs-lookup"><span data-stu-id="c7fd4-102">Example: Handling Exceptions When Binding Data</span></span>

> [!NOTE]
> <span data-ttu-id="c7fd4-103">En este tema se hace referencia a .NET Native Developer Preview, que es una versión preliminar del software.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="c7fd4-104">Puede descargar esta versión preliminar desde el [sitio web de Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (es necesario registrarse).</span><span class="sxs-lookup"><span data-stu-id="c7fd4-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="c7fd4-105">En el ejemplo siguiente se muestra cómo resolver una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md) que se produce cuando una aplicación compilada con la cadena de herramientas de .net Native intenta enlazar datos.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-105">The following example shows how to resolve a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the .NET Native tool chain tries to bind data.</span></span> <span data-ttu-id="c7fd4-106">Esta es la información de la excepción:</span><span class="sxs-lookup"><span data-stu-id="c7fd4-106">Here’s the exception information:</span></span>  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="c7fd4-107">Esta es la pila de llamadas asociada:</span><span class="sxs-lookup"><span data-stu-id="c7fd4-107">Here's the associated call stack:</span></span>  
  
```output
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="c7fd4-108">¿Qué estaba haciendo la aplicación?</span><span class="sxs-lookup"><span data-stu-id="c7fd4-108">What was the app doing?</span></span>  

 <span data-ttu-id="c7fd4-109">En la base de la pila, los marcos del <xref:Windows.UI.Xaml?displayProperty=nameWithType> espacio de nombres indican que el motor de representación XAML se estaba ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-109">At the base of the stack, frames from the <xref:Windows.UI.Xaml?displayProperty=nameWithType> namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="c7fd4-110">El uso del método <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> indica una búsqueda basada en la reflexión del valor de una propiedad en el tipo cuyos metadatos se han quitado.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="c7fd4-111">El primer paso para proporcionar una directiva de metadatos sería agregar metadatos `serialize` para el tipo de forma que sus propiedades sean accesibles:</span><span class="sxs-lookup"><span data-stu-id="c7fd4-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="c7fd4-112">¿Es un caso aislado?</span><span class="sxs-lookup"><span data-stu-id="c7fd4-112">Is this an isolated case?</span></span>  

 <span data-ttu-id="c7fd4-113">En este escenario, si el enlace de datos tiene metadatos incompletos para un `ViewModel`, es posible que también los tenga para otros.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="c7fd4-114">Si el código está estructurado de forma que todos los modelos de vista de la aplicación están incluidos en el espacio de nombres `App.ViewModels`, se podría usar una directiva en tiempo de ejecución más general:</span><span class="sxs-lookup"><span data-stu-id="c7fd4-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="c7fd4-115">¿Se podría volver a escribir el código para que no use la reflexión?</span><span class="sxs-lookup"><span data-stu-id="c7fd4-115">Could the code be rewritten to not use reflection?</span></span>  

 <span data-ttu-id="c7fd4-116">Los enlaces de datos hacen un uso intensivo de la reflexión, de modo que cambiar el código para evitar la reflexión no es factible.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="c7fd4-117">Sin embargo, hay formas de especificar el `ViewModel` en la página XAML para que la cadena de herramientas pueda asociar enlaces de propiedad con el tipo correcto en tiempo de compilación y mantener los metadatos sin usar una directiva en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="c7fd4-118">Por ejemplo, podría aplicar el <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> atributo en las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-118">For example, you could apply the <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> attribute on properties.</span></span> <span data-ttu-id="c7fd4-119">Esto hace que el compilador XAML genere la información de búsqueda necesaria y permite prescindir de una directiva en tiempo de ejecución en el archivo Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="c7fd4-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fd4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7fd4-120">See also</span></span>

- [<span data-ttu-id="c7fd4-121">Introducción</span><span class="sxs-lookup"><span data-stu-id="c7fd4-121">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="c7fd4-122">Ejemplo: solucionar problemas de programación dinámica</span><span class="sxs-lookup"><span data-stu-id="c7fd4-122">Example: Troubleshooting Dynamic Programming</span></span>](example-troubleshooting-dynamic-programming.md)
