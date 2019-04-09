---
title: Interoperabilidad entre WPF y Direct3D9
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 04a668ea18177d2a174569f064d9102239dd5e7d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199328"
---
# <a name="wpf-and-direct3d9-interoperation"></a>Interoperabilidad entre WPF y Direct3D9
Puede incluir contenido Direct3D9 en una aplicación de Windows Presentation Foundation (WPF). Este tema describe cómo crear contenido Direct3D9 para que interopere eficazmente con WPF.  
  
> [!NOTE]
>  Cuando se usa contenido Direct3D9 en WPF, también deberá pensar en rendimiento. Para obtener más información acerca de cómo optimizar el rendimiento, consulte [consideraciones de rendimiento para la interoperabilidad de WPF y Direct3D9](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Búferes de pantalla  
 El <xref:System.Windows.Interop.D3DImage> clase administra dos búferes de pantalla, que se denominan el *búfer de reserva* y *búfer frontal*. El búfer de reserva es la superficie de Direct3D9. Los cambios realizados en el búfer de reserva se copian en el búfer frontal cuando se llama a la <xref:System.Windows.Interop.D3DImage.Unlock%2A> método.  
  
 La siguiente ilustración muestra la relación entre el búfer de reserva y el búfer frontal.  
  
 ![Búferes de pantalla de D3DImage](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Creación de dispositivos de Direct3D9  
 Para representar contenido Direct3D9, debe crear un dispositivo de Direct3D9. Hay dos objetos Direct3D9 que puede usar para crear un dispositivo, `IDirect3D9` y `IDirect3D9Ex`. Utilice estos objetos para crear `IDirect3DDevice9` y `IDirect3DDevice9Ex` dispositivos, respectivamente.  
  
 Crear un dispositivo mediante una llamada a uno de los métodos siguientes.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 En Windows Vista o un sistema operativo posterior, utilice el `Direct3DCreate9Ex` método con una visualización que está configurada para usar el modelo de controladores de pantalla de Windows (WDDM). Use el `Direct3DCreate9` método en cualquier otra plataforma.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Disponibilidad del método Direct3DCreate9Ex  
 Tiene la d3d9.dll el `Direct3DCreate9Ex` método sólo en Windows Vista o un sistema operativo posterior. Si vincula directamente la función en Windows XP, la aplicación no se puede cargar. Para determinar si el `Direct3DCreate9Ex` se admite el método, cargar el archivo DLL y busque la dirección del procedimiento. El código siguiente muestra cómo probar la `Direct3DCreate9Ex` método. Para obtener un ejemplo de código completo, vea [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>Creación de HWND  
 Creación de un dispositivo requiere un HWND. En general, se crea un HWND ficticio para Direct3D9 usar. El ejemplo de código siguiente muestra cómo crear un HWND ficticio.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Parámetros presentes  
 Creación de un dispositivo también requiere un `D3DPRESENT_PARAMETERS` struct, pero sólo unos cuantos parámetros son importantes. Estos parámetros se eligen para minimizar el consumo de memoria.  
  
 Establecer el `BackBufferHeight` y `BackBufferWidth` campos en 1. Si ellos en 0, que se establezcan para las dimensiones de HWND.  
  
 Establezca siempre la `D3DCREATE_MULTITHREADED` y `D3DCREATE_FPU_PRESERVE` marcas para evitar dañar la memoria utilizada por Direct3D9 e impedir que cambiar la configuración de la FPU Direct3D9.  
  
 El código siguiente muestra cómo inicializar el `D3DPRESENT_PARAMETERS` struct.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Crear el destino de representación del búfer de reserva  
 Para mostrar contenido Direct3D9 en un <xref:System.Windows.Interop.D3DImage>, cree una superficie de Direct3D9 y asignar un valor mediante una llamada a la <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> método.  
  
### <a name="verifying-adapter-support"></a>Comprobando la compatibilidad del adaptador  
 Antes de crear una superficie, compruebe que todos los adaptadores admiten las propiedades de superficie que requiere. Incluso si se procesa en un único adaptador, la ventana de WPF puede mostrarse en cualquier adaptador en el sistema. Siempre debería escribir código de Direct3D9 que controla las configuraciones de varios adaptadores, y debe comprobar todos los adaptadores para obtener soporte técnico, dado que WPF puede mover la superficie de entre los adaptadores disponibles.  
  
 En el ejemplo de código siguiente se muestra cómo comprobar todos los adaptadores en el sistema de Direct3D9 admiten.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>Creación de la superficie  
 Antes de crear una superficie, compruebe que las capacidades de dispositivo compatible con buen rendimiento en el sistema operativo de destino. Para obtener más información, consulte [consideraciones de rendimiento para la interoperabilidad de WPF y Direct3D9](performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 Cuando haya comprobado las capacidades del dispositivo, puede crear la superficie. El ejemplo de código siguiente muestra cómo crear el destino de representación.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 En Windows Vista y sistemas operativos posteriores, que están configurados para usar el WDDM, puede crear una textura de destino de representación y pasar a la superficie de nivel 0 para el <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> método. No se recomienda este enfoque en Windows XP, porque no se puede crear una textura de destino de representación bloqueable y se reducirá el rendimiento.  
  
## <a name="handling-device-state"></a>Controlar el estado de dispositivo  
 El <xref:System.Windows.Interop.D3DImage> clase administra dos búferes de pantalla, que se denominan el *búfer de reserva* y *búfer frontal*. El búfer de reserva es la superficie de Direct3D.  Los cambios realizados en el búfer de reserva se copian en el búfer frontal cuando se llama a la <xref:System.Windows.Interop.D3DImage.Unlock%2A> método, donde se muestran en el hardware. En ocasiones, el búfer frontal deja de estar disponible. Esta falta de disponibilidad puede deberse a bloqueo de pantalla, aplicaciones Direct3D exclusivas de pantalla completa, un cambio de usuario u otras actividades del sistema. Cuando esto ocurre, se notifica a la aplicación de WPF controlando el <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> eventos.  Cómo responde la aplicación en el búfer frontal estar disponible depende de si WPF está habilitado para revertir a la representación de software. El <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> método tiene una sobrecarga que toma un parámetro que especifica si WPF recurre a la representación de software.  
  
 Cuando se llama a la <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> sobrecargar o llamar a la <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> sobrecarga con el `enableSoftwareFallback` parámetro establecido en `false`, el sistema de representación libera su referencia al búfer de reserva cuando el búfer frontal deja de estar disponible y no hay nada muestra. Cuando el búfer frontal esté disponible de nuevo, el sistema de representación provoca la <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> eventos para notificar a la aplicación de WPF.  Puede crear un controlador de eventos para el <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> eventos para reiniciar la representación de nuevo con una superficie de Direct3D válida. Para reiniciar la representación, debe llamar a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 Cuando se llama a la <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> sobrecarga con el `enableSoftwareFallback` parámetro establecido en `true`, el sistema de representación conserva su referencia al búfer de reserva cuando el búfer frontal deja de estar disponible, por lo que no hay ninguna necesidad de llamar a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> al frente búfer esté disponible de nuevo.  
  
 Cuando se habilita la representación de software, puede haber situaciones donde el dispositivo del usuario deja de estar disponible, pero el sistema de representación mantiene una referencia a la superficie de Direct3D. Para comprobar si un dispositivo de Direct3D9 no está disponible, llame a la `TestCooperativeLevel` método. Para comprobar una llamada de dispositivos Direct3D9Ex el `CheckDeviceState` método, porque el `TestCooperativeLevel` método está en desuso y siempre devuelve un valor correcto. Si no está disponible el dispositivo del usuario, llame a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> para liberar la referencia de WPF en el búfer de reserva.  Si necesita restablecer el dispositivo, llame a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> con el `backBuffer` parámetro establecido en `null`y, a continuación, llame a <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> nuevo con `backBuffer` establecido en una superficie de Direct3D válida.  
  
 Llame a la `Reset` método para recuperarse de un dispositivo no es válido únicamente si implementa la compatibilidad con varios adaptador. En caso contrario, liberar todas las interfaces de Direct3D9 y volver a crear completamente. Si ha cambiado el diseño del adaptador, no se actualizan los objetos de Direct3D9 creados antes del cambio.  
  
## <a name="handling-resizing"></a>Cambiar el tamaño de control  
 Si un <xref:System.Windows.Interop.D3DImage> se muestra en una resolución distinta de su tamaño nativo, se escala según actual <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, salvo que <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> se sustituye por <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Si necesita una mayor fidelidad, debe crear una nueva superficie cuando el contenedor de la <xref:System.Windows.Interop.D3DImage> cambia de tamaño.  
  
 Existen tres posibles enfoques para controlar el cambio de tamaño.  
  
-   Participar en el sistema de diseño y creación de una superficie de nuevo cuando cambia el tamaño. No cree demasiadas superficies, porque puede agotar o fragmentar la memoria de vídeo.  
  
-   Espere hasta que no ha producido un evento de cambio de tamaño para un período de tiempo para crear la nueva superficie fijo.  
  
-   Crear un <xref:System.Windows.Threading.DispatcherTimer> que comprueba las dimensiones del contenedor varias veces por segundo.  
  
## <a name="multi-monitor-optimization"></a>Optimización de varios monitor  
 Puede dar lugar a la reducción significativa del rendimiento cuando el sistema de representación se mueve un <xref:System.Windows.Interop.D3DImage> a otro monitor.  
  
 En el WDDM, siempre y cuando los monitores que se encuentran en el mismo vídeo tarjeta y usa `Direct3DCreate9Ex`, no hay ninguna reducción del rendimiento. Si los monitores se encuentran en las tarjetas de vídeo independientes, se reduce el rendimiento. En Windows XP, siempre se reduce el rendimiento.  
  
 Cuando el <xref:System.Windows.Interop.D3DImage> se mueve a otro monitor, puede crear una superficie de nuevo en el adaptador correspondiente para restaurar un buen rendimiento.  
  
 Para evitar la disminución del rendimiento, escribir código específicamente para el caso de varios monitor. En la lista siguiente se muestra una forma de escribir código de varios monitor.  
  
1.  Buscar un punto de la <xref:System.Windows.Interop.D3DImage> en el espacio de pantalla con la `Visual.ProjectToScreen` método.  
  
2.  Use el `MonitorFromPoint` método GDI para buscar el monitor que muestra el punto.  
  
3.  Use el `IDirect3D9::GetAdapterMonitor` método para buscar qué adaptador de Direct3D9 el monitor se encuentra en.  
  
4.  Si el adaptador no es el mismo que el adaptador con el búfer de reserva, cree un nuevo búfer de reserva en el nuevo monitor y asígnelo a la <xref:System.Windows.Interop.D3DImage> búfer de reserva.  
  
> [!NOTE]
>  Si el <xref:System.Windows.Interop.D3DImage> sobrepasa los monitores, rendimiento será lentos, excepto en el caso de WDDM y `IDirect3D9Ex` en el mismo adaptador. No hay ninguna manera de mejorar el rendimiento en esta situación.  
  
 El ejemplo de código siguiente muestra cómo buscar al monitor actual.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Actualizar el monitor cuando el <xref:System.Windows.Interop.D3DImage> cambios de tamaño o posición del contenedor o actualizar el monitor mediante el uso de un `DispatcherTimer` que actualiza varias veces por segundo.  
  
## <a name="wpf-software-rendering"></a>Representación de Software de WPF  
 WPF representa sincrónicamente en el subproceso de interfaz de usuario en el software en las situaciones siguientes.  
  
-   Impresión  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 Cuando se produce una de estas situaciones, el sistema de representación llama el <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> método para copiar el búfer de hardware al software. La implementación predeterminada llama el `GetRenderTargetData` método con su superficie. Dado que esta llamada se produce fuera del patrón de bloqueo/desbloqueo, puede producir un error. En este caso, el `CopyBackBuffer` devuelve del método `null` y no se muestra ninguna imagen.  
  
 Puede invalidar el <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> método, llame a la implementación base, y si devuelve `null`, puede devolver un marcador de posición <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 También puede implementar su propia representación de software en lugar de llamar a la implementación base.  
  
> [!NOTE]
>  Si WPF está representando completamente en software, <xref:System.Windows.Interop.D3DImage> no se muestra porque WPF no tiene un búfer frontal.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.D3DImage>
- [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Tutorial: Hospedar contenido Direct3D9 en WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
