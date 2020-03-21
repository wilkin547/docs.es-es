---
title: 'Ejemplo: control de excepciones al enlazar datos'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
ms.openlocfilehash: b774d1bce4f4d1c03258ed44b27d3871e7c5275f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181021"
---
# <a name="example-handling-exceptions-when-binding-data"></a>Ejemplo: control de excepciones al enlazar datos
> [!NOTE]
> En este tema se hace referencia a .NET Native Developer Preview, que es una versión preliminar del software. Puede descargar esta versión preliminar desde el [sitio web de Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (es necesario registrarse).  
  
 En el ejemplo siguiente se muestra cómo resolver una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md) que se produce cuando una aplicación compilada con la cadena de herramientas de .NET Native intenta enlazar datos. Esta es la información de la excepción:  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:
App.ViewModels.MainPageVM  
```  
  
 Esta es la pila de llamadas asociada:  
  
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
  
## <a name="what-was-the-app-doing"></a>¿Qué estaba haciendo la aplicación?  
 En la base de la <xref:Windows.UI.Xaml?displayProperty=nameWithType> pila, los fotogramas del espacio de nombres indican que el motor de representación XAML se estaba ejecutando.   El uso del método <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> indica una búsqueda basada en la reflexión del valor de una propiedad en el tipo cuyos metadatos se han quitado.  
  
 El primer paso para proporcionar una directiva de metadatos sería agregar metadatos `serialize` para el tipo de forma que sus propiedades sean accesibles:  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a>¿Es un caso aislado?  
 En este escenario, si el enlace de datos tiene metadatos incompletos para un `ViewModel`, es posible que también los tenga para otros.  Si el código está estructurado de forma que todos los modelos de vista de la aplicación están incluidos en el espacio de nombres `App.ViewModels`, se podría usar una directiva en tiempo de ejecución más general:  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a>¿Se podría volver a escribir el código para que no use la reflexión?  
 Los enlaces de datos hacen un uso intensivo de la reflexión, de modo que cambiar el código para evitar la reflexión no es factible.  
  
 Sin embargo, hay formas de especificar el `ViewModel` en la página XAML para que la cadena de herramientas pueda asociar enlaces de propiedad con el tipo correcto en tiempo de compilación y mantener los metadatos sin usar una directiva en tiempo de ejecución.  Por ejemplo, podría <xref:Windows.UI.Xaml.Data.BindableAttribute?displayProperty=nameWithType> aplicar el atributo en las propiedades. Esto hace que el compilador XAML genere la información de búsqueda necesaria y permite prescindir de una directiva en tiempo de ejecución en el archivo Default.rd.xml.  
  
## <a name="see-also"></a>Consulte también

- [Introducción](getting-started-with-net-native.md)
- [Ejemplo: solucionar problemas de programación dinámica](example-troubleshooting-dynamic-programming.md)
