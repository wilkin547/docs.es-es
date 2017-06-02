---
title: "Interoperabilidad entre WPF y Direct3D9 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9 [interoperabilidad de WPF], crear contenido Direct3D9"
  - "WPF, crear contenido Direct3D9"
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Interoperabilidad entre WPF y Direct3D9
Puede incluir contenido de Direct3D9 en una aplicación de Windows Presentation Foundation \(WPF\).  En este tema se describe cómo crear contenido de Direct3D9 de modo que interopere eficazmente con WPF.  
  
> [!NOTE]
>  Cuando se utiliza contenido de Direct3D9 en WPF, también es preciso pensar en el rendimiento.  Para obtener más información acerca de cómo optimizar el rendimiento, vea [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## Búferes de presentación  
 La clase <xref:System.Windows.Interop.D3DImage> administra dos búferes de presentación, denominados *búfer de reserva* y *búfer frontal*.  El búfer de reserva es la superficie de Direct3D.  Los cambios en el búfer de reserva se copian en el búfer frontal cuando se llama al método <xref:System.Windows.Interop.D3DImage.Unlock%2A>.  
  
 La ilustración siguiente muestra la relación entre el búfer de reserva y el búfer frontal.  
  
 ![Búferes de pantalla de D3DImage](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage\_buffers")  
  
## Creación de dispositivos de Direct3D9  
 Para representar contenido de Direct3D9, debe crear un dispositivo de Direct3D9.  Hay dos objetos Direct3D9 que puede utilizar para crear un dispositivo, `IDirect3D9` e `IDirect3D9Ex`.  Utilice estos objetos para crear los dispositivos `IDirect3DDevice9` e `IDirect3DDevice9Ex`, respectivamente.  
  
 Para crear dispositivo, llame a uno de los métodos siguientes.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 En Windows Vista o sistema operativo posterior, utilice el método de `Direct3DCreate9Ex` con una presentación configurada para utilizar el controlador de vídeo Model \(WDDM\) de Windows.  Utilice el método `Direct3DCreate9` en todas las demás plataformas.  
  
### Disponibilidad del método Direct3DCreate9Ex  
 El archivo d3d9.dll tiene el método de `Direct3DCreate9Ex` sólo en Windows Vista o sistema operativo posterior.  Si vincula directamente la función en Windows XP, la aplicación no se cargará.  Para determinar si el método `Direct3DCreate9Ex` se admite, cargue la DLL y busque la dirección de procedimiento.  En el código siguiente se muestra cómo comprobar el método `Direct3DCreate9Ex`.  Para obtener un ejemplo de código completo, vea [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### Creación de HWND  
 Para crear un dispositivo se requiere un HWND.  En general, se crea un HWND ficticio para que Direct3D9 lo utilice.  En el ejemplo de código siguiente se muestra cómo crear un HWND ficticio.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### Parámetros presentes  
 Para crear un dispositivo, también se requiere un struct `D3DPRESENT_PARAMETERS`, pero únicamente son importantes algunos parámetros.  Estos parámetros se eligen para minimizar la superficie de memoria.  
  
 Establezca los campos `BackBufferHeight` y `BackBufferWidth` en 1.  Establecerlos en 0 hace que se establezcan en las dimensiones de HWND.  
  
 Siempre establezca las marcas `D3DCREATE_MULTITHREADED` y `D3DCREATE_FPU_PRESERVE` para evitar que se dañe la memoria utilizada por Direct3D9 y que Direct3D9 cambie los valores de FPU.  
  
 En el código siguiente se muestra cómo inicializar el struct `D3DPRESENT_PARAMETERS`.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## Crear el destino de representación del búfer de reserva  
 Para mostrar el contenido de Direct3D9 en <xref:System.Windows.Interop.D3DImage>, cree una superficie de Direct3D9 y asígnela llamando al método <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
### Comprobar la compatibilidad del adaptador  
 Antes de crear una superficie, compruebe que todos los adaptadores admiten las propiedades de superficie que se necesitan.  Aunque represente en un único adaptador, la ventana de WPF se puede mostrarse en cualquier adaptador del sistema.  Siempre se debe escribir código de Direct3D9 que administre configuraciones de varios adaptadores. Además, deberá comprobar la compatibilidad de todos los adaptadores, porque WPF podría mover la superficie entre los adaptadores disponibles.  
  
 En el ejemplo de código siguiente se muestra cómo comprobar si todos los adaptadores del sistema son compatibles con Direct3D9.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### Crear la superficie  
 Antes de crear una superficie, compruebe que las capacidades de dispositivo admiten un rendimiento adecuado en el sistema operativo de destino.  Para obtener más información, vea [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Cuando haya comprobado las capacidades del dispositivo, puede crear la superficie.  En el ejemplo de código siguiente se muestra cómo crear el destino de representación.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### WDDM  
 En Windows Vista y sistemas operativos posteriores, que se configuran para usar el WDDM, puede crear una textura de destino de representación y pasar la superficie de nivel 0 al método de <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> .  Este enfoque no se recomienda en Windows XP, porque no se puede crear una textura de destino de representación bloqueable y se reducirá el rendimiento.  
  
## Administrar el estado del dispositivo  
 La clase <xref:System.Windows.Interop.D3DImage> administra dos búferes de presentación, denominados *búfer de reserva* y *búfer frontal*.  El búfer de reserva es la superficie de Direct3D.  Los cambios en el búfer de reserva se copian en el búfer frontal cuando se llama al método de <xref:System.Windows.Interop.D3DImage.Unlock%2A> , donde se muestran en el hardware.  En ocasiones, el búfer frontal no esté disponible.  Esta falta de disponibilidad puede ser debida a un bloqueo de la pantalla, aplicaciones Direct3D exclusivas de pantalla completa, un cambio de usuario u otras actividades del sistema.  Cuando ocurre esto, la aplicación WPF es notificada controlando el evento de <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> .  Cómo la aplicación responde al búfer frontal que no esté disponible depende de si WPF está habilitado para recurrir a la representación de software.  El método de <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> tiene una sobrecarga que toma un parámetro que especifique si WPF recurrir a la representación de software.  
  
 Cuando se llama a la sobrecarga de <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> o llama a la sobrecarga de <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> con el parámetro de `enableSoftwareFallback` establecido en `false`, el sistema de representación libera su referencia en el búfer de reserva cuando el búfer frontal no esté disponible y no se muestra nada.  Cuando el búfer frontal está disponible de nuevo, el sistema de representación provoca el evento de <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> para notificar a la aplicación de WPF.  Puede crear un controlador de eventos para el evento de <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> reinicie mostrar de nuevo con una superficie válida de Direct3D.  Para reiniciar la representación, debe llamar a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 Cuando se llama a la sobrecarga de <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> con el parámetro de `enableSoftwareFallback` establecido en `true`, el sistema de representación conserva su referencia al búfer de reserva cuando el búfer frontal no esté disponible, por lo que no hay necesidad de llamar a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> cuando el búfer frontal está disponible de nuevo.  
  
 Cuando se habilita la presentación de software, puede haber situaciones donde el dispositivo de usuario no esté disponible, pero el sistema de representación mantiene una referencia a la superficie de Direct3D.  Para comprobar si un dispositivo de Direct3D9 no esté disponible, llame al método de `TestCooperativeLevel` .  Para comprobar los dispositivos de un Direct3D9Ex llame al método de `CheckDeviceState` , porque el método de `TestCooperativeLevel` está obsoleto y siempre devuelve correctamente.  Si el dispositivo de usuario ha protegido de estar disponible, llamada <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> para liberar la referencia de WPF en el búfer de reserva.  Si necesita restaurar el dispositivo, llame a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> con el parámetro de `backBuffer` establecido en `null`, y llame a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> de nuevo con `backBuffer` establecido una superficie válida de Direct3D.  
  
 Llame al método `Reset` para recuperarse de un dispositivo no válido únicamente si implementa la compatibilidad con varios adaptadores.  De lo contrario, libere todas las interfaces de Direct3D9 y créelas de nuevo completamente.  Si el diseño del adaptador ha cambiado, los objetos de Direct3D9 creados antes del cambio no se actualizan.  
  
## Administrar los cambios de tamaño  
 Si <xref:System.Windows.Interop.D3DImage> se muestra en una resolución distinta de su tamaño nativo, se escala según <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>actual, salvo que <xref:System.Windows.Media.Effects.SamplingMode> se sustituye para <xref:System.Windows.Media.BitmapScalingMode>.  
  
 Si necesita  una fidelidad mayor, debe crear una nueva superficie cuando el contenedor de <xref:System.Windows.Interop.D3DImage> cambie de tamaño.  
  
 Hay tres posibles enfoques para administrar los cambios de tamaño.  
  
-   Participe en el sistema de diseño y cree una nueva superficie cuando el tamaño cambie.  No cree demasiadas superficies, porque puede agotar o fragmentar la memoria de vídeo.  
  
-   Para crear la nueva superficie, espere hasta que transcurra un período de tiempo fijo durante el que no se haya producido ningún evento de cambio de tamaño.  
  
-   Cree un objeto <xref:System.Windows.Threading.DispatcherTimer> que comprueba las dimensiones del contenedor varias veces por segundo.  
  
## Optimización de varios monitores  
 Cuando el sistema de representación mueve un objeto <xref:System.Windows.Interop.D3DImage> a otro monitor, el rendimiento se puede reducir de manera significativa.  
  
 En el WDDM, siempre que los monitores se encuentren en la misma tarjeta de vídeo y se utilice `Direct3DCreate9Ex`, el rendimiento no se reduce en absoluto.  Si los monitores se encuentran en tarjetas de vídeo independientes, se reduce el rendimiento.  En Windows XP, el rendimiento se reduce siempre.  
  
 Cuando se mueve el objeto <xref:System.Windows.Interop.D3DImage> a otro monitor, puede crear una nueva superficie en el adaptador correspondiente para restaurar el rendimiento adecuado.  
  
 Para evitar la reducción del rendimiento, escriba el código específicamente para varios monitores.  En la lista siguiente se muestra una manera de escribir código para varios monitores.  
  
1.  Busque un punto de <xref:System.Windows.Interop.D3DImage> en el espacio de la pantalla con el método `Visual.ProjectToScreen`.  
  
2.  Utilice el método `MonitorFromPoint` GDI para buscar el monitor que muestra ese punto.  
  
3.  Utilice el método `IDirect3D9::GetAdapterMonitor` para buscar en qué adaptador de Direct3D9 se encuentra el monitor.  
  
4.  Si el adaptador no es el mismo que tiene el búfer de reserva, cree un nuevo búfer de reserva en el nuevo monitor y asígnelo al búfer de reserva de <xref:System.Windows.Interop.D3DImage>.  
  
> [!NOTE]
>  Si <xref:System.Windows.Interop.D3DImage> abarca dos o más monitores, el rendimiento será lento, excepto si el WDDM e `IDirect3D9Ex` están en el mismo adaptador.  No hay ninguna manera de mejorar el rendimiento en esta situación.  
  
 En el ejemplo de código siguiente se muestra cómo buscar el monitor actual.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Actualice el monitor cuando cambie la posición o el tamaño del contenedor de <xref:System.Windows.Interop.D3DImage>, o bien actualice el monitor mediante un objeto `DispatcherTimer` que se actualiza varias veces por segundo.  
  
## Representación de software de WPF  
 WPF representa sincrónicamente en el subproceso de la interfaz de usuario en el software en las situaciones siguientes.  
  
-   Impresión  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Cuando sucede una de estas situaciones, el sistema de representación llama al método <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> para que copie el búfer de hardware en el software.  La implementación predeterminada llama al método `GetRenderTargetData` con la superficie.  Dado que esta llamada se produce fuera del modelo bloquear\/desbloquear, puede producirse un error.  En este caso, el método `CopyBackBuffer` devuelve `null` y no se muestra ninguna imagen.  
  
 Puede invalidar el método <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>, llamar a la implementación base y, si devuelve `null`, puede devolver un objeto <xref:System.Windows.Media.Imaging.BitmapSource> de marcador de posición.  
  
 También puede implementar su propia representación de software en lugar de llamar a la implementación base.  
  
> [!NOTE]
>  Si WPF efectúa la representación completamente en software, <xref:System.Windows.Interop.D3DImage> no se muestra, porque WPF no tiene un búfer frontal.  
  
## Vea también  
 <xref:System.Windows.Interop.D3DImage>   
 [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [Tutorial: Hospedar contenido Direct3D9 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)