---
title: "Ejemplo: solucionar problemas de programaci&#243;n din&#225;mica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Ejemplo: solucionar problemas de programaci&#243;n din&#225;mica
> [!NOTE]
>  En este tema se hace referencia a .NET Native Developer Preview, que es una versión preliminar del software.  Puede descargar esta vista previa desde el [sitio web de Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=394611) \(es necesario registrarse\).  
  
 No todos los errores de búsqueda de metadatos en aplicaciones desarrolladas con la cadena de herramientas de [!INCLUDE[net_native](../../../includes/net-native-md.md)] tienen como resultado una excepción.  Algunos pueden manifestarse de manera impredecible en una aplicación.  En el ejemplo siguiente se muestra una infracción de acceso causada por hacer referencia a un objeto nulo:  
  
```  
  
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
  
 Vamos a intentar solucionar esta excepción mediante el enfoque de tres pasos descrito en la sección “Resolver manualmente los metadatos que faltan” de [Introducción](../../../docs/framework/net-native/getting-started-with-net-native.md).  
  
## ¿Qué estaba haciendo la aplicación?  
 Lo primero que hay tener en cuenta es la maquinaria de la palabra clave `async` en la base de la pila.  Determinar lo que la aplicación estaba haciendo realmente en un método `async` puede ser problemático, ya que la pila ha perdido el contexto de la llamada original y ha ejecutado el código `async` en un subproceso diferente.  Sin embargo, podemos deducir que la aplicación estaba intentando cargar su primera página.  En la implementación de `NavigationArgs.Setup`, el código siguiente produjo la infracción de acceso:  
  
```  
AppViewModel.Current.LayoutVM.PageMap  
```  
  
 En este caso, la propiedad `LayoutVM` en `AppViewModel.Current` era **null**.  Alguna ausencia de metadatos provocó una diferencia de comportamiento que provocó que una propiedad tuviese un estado no inicializado en vez de establecido, como esperaba la aplicación.  Establecer un punto de interrupción en el código donde `LayoutVM` debería haberse inicializado podría arrojar luz sobre la situación.  Sin embargo, tenga en cuenta que el tipo de `LayoutVM` es `App.Core.ViewModels.Layout.LayoutApplicationVM`.  La única directiva de metadatos presente en el archivo rd.xml es:  
  
```  
  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
  
```  
  
 Una causa probable del error es que a `App.Core.ViewModels.Layout.LayoutApplicationVM` le falten metadatos porque está en un espacio de nombres diferente.  
  
 En este caso, agregar una directiva de tiempo de ejecución para `App.Core.ViewModels` ha resuelto el problema.  La causa principal fue una llamada de la API al método <xref:System.Type.GetType%28System.String%29?displayProperty=fullName> que devolvió **null**, y la aplicación omitió el problema de forma silenciosa hasta que se produjo un bloqueo.  
  
 En programación dinámica, una buena práctica cuando se utilizan las API de reflexión en [!INCLUDE[net_native](../../../includes/net-native-md.md)] consiste en usar las sobrecargas <xref:System.Type.GetType%2A?displayProperty=fullName> que generan una excepción en caso de error.  
  
## ¿Es un caso aislado?  
 También pueden surgir otros problemas al utilizar `App.Core.ViewModels`.  Debe decidir si merece la pena identificar y corregir cada excepción debida a la falta de metadatos, o ahorrar tiempo y agregar directivas para una clase más grande de tipos.  Aquí, agregar metadatos `dynamic` para `App.Core.ViewModels` podría ser el mejor método si el aumento de tamaño resultante del archivo binario de salida no supone un problema.  
  
## ¿Podría modificarse el código?  
 Si la aplicación hubiera usado `typeof(LayoutApplicationVM)` en lugar de `Type.GetType(“LayoutApplicationVM”)`, la cadena de herramientas podría haber conservado los metadatos de `browse`.  Sin embargo, aun así no habría creado metadatos de `invoke`, que habrían producido una excepción [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) al crear una instancia del tipo.  Para evitar la excepción, se tendría que agregar una directiva de tiempo de ejecución para el espacio de nombres o el tipo que especifica la directiva `dynamic`.  Para obtener información sobre las directivas de tiempo de ejecución, consulte [Referencia del archivo de configuración de directivas en tiempo de ejecución \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
## Vea también  
 [Introducción](../../../docs/framework/net-native/getting-started-with-net-native.md)   
 [Ejemplo: control de excepciones al enlazar datos](../../../docs/framework/net-native/example-handling-exceptions-when-binding-data.md)