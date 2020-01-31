---
title: Consideraciones de rendimiento para la interoperabilidad de Direct3D9 y WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 2445732c27d210a41da26303d6a9ce07ef6fcc94
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743934"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF
Puede hospedar contenido de Direct3D9 mediante la clase <xref:System.Windows.Interop.D3DImage>. El hospedaje de contenido de Direct3D9 puede afectar al rendimiento de la aplicación. En este tema se describen los procedimientos recomendados para optimizar el rendimiento al hospedar contenido de Direct3D9 en una aplicación Windows Presentation Foundation (WPF). Estos procedimientos recomendados incluyen cómo usar <xref:System.Windows.Interop.D3DImage> y prácticas recomendadas cuando se usa Windows Vista, Windows XP y pantallas de varios monitores.  
  
> [!NOTE]
> Para ver ejemplos de código que muestran estos procedimientos recomendados, consulte [interoperabilidad de WPF y Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Usar D3DImage moderadamente  
 El contenido de Direct3D9 hospedado en una instancia de <xref:System.Windows.Interop.D3DImage> no se representa tan rápido como en una aplicación de Direct3D pura. Copiar la superficie y vaciar el búfer de comandos puede ser una operación costosa. A medida que aumenta el número de instancias de <xref:System.Windows.Interop.D3DImage>, se producen más vaciados y se degrada el rendimiento. Por lo tanto, debe usar <xref:System.Windows.Interop.D3DImage> moderadamente.  
  
## <a name="best-practices-on-windows-vista"></a>Prácticas recomendadas en Windows Vista  
 Para obtener el mejor rendimiento en Windows Vista con una pantalla que está configurada para usar el modelo de controladores de pantalla de Windows (WDDM), cree la superficie de Direct3D9 en un dispositivo `IDirect3DDevice9Ex`. Esto permite el uso compartido de la superficie. La tarjeta de vídeo debe admitir las capacidades del controlador `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` y `D3DCAPS2_CANSHARERESOURCE` en Windows Vista. Cualquier otra configuración hace que la superficie se copie a través del software, lo que reduce significativamente el rendimiento.  
  
> [!NOTE]
> Si Windows Vista tiene una pantalla que está configurada para usar el modelo de controladores de pantalla de Windows XP (XDDM), la superficie siempre se copia a través del software, independientemente de la configuración. Con la tarjeta de vídeo y la configuración apropiadas, verá un mejor rendimiento en Windows Vista cuando use el WDDM, ya que las copias de superficie se realizan en el hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Prácticas recomendadas en Windows XP  
 Para obtener el mejor rendimiento en Windows XP, que usa el modelo de controladores de pantalla de Windows XP (XDDM), cree una superficie bloqueable que se comporta correctamente cuando se llama al método `IDirect3DSurface9::GetDC`. Internamente, el método `BitBlt` transfiere la superficie entre dispositivos en el hardware. El método `GetDC` siempre funciona en superficies XRGB. Sin embargo, si el equipo cliente ejecuta Windows XP con SP3 o SP2, y si el cliente también tiene la revisión para la característica de ventana en capas, este método solo funciona en superficies ARGB. La tarjeta de vídeo debe admitir la funcionalidad del controlador `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES`.  
  
 Una profundidad de pantalla de escritorio de 16 bits puede reducir considerablemente el rendimiento. Se recomienda usar un escritorio de 32 bits.  
  
 Si va a desarrollar para Windows Vista y Windows XP, pruebe el rendimiento en Windows XP. La falta de memoria de vídeo en Windows XP es un problema. Además, <xref:System.Windows.Interop.D3DImage> en Windows XP usa más memoria de vídeo y ancho de banda que el WDDM de Windows Vista, debido a una copia de memoria de vídeo adicional necesaria. Por lo tanto, puede esperar que el rendimiento sea peor en Windows XP que en Windows Vista para el mismo hardware de vídeo.  
  
> [!NOTE]
> El XDDM está disponible en Windows XP y Windows Vista; sin embargo, WDDM solo está disponible en Windows Vista.  
  
## <a name="general-best-practices"></a>Procedimientos recomendados generales  
 Al crear el dispositivo, use la marca de creación `D3DCREATE_MULTITHREADED`. Esto reduce el rendimiento, pero el sistema de representación de WPF llama a los métodos de este dispositivo desde otro subproceso. Asegúrese de seguir el protocolo de bloqueo correctamente, de modo que no haya dos subprocesos que tengan acceso al dispositivo al mismo tiempo.  
  
 Si la representación se realiza en un subproceso administrado de WPF, se recomienda encarecidamente que cree el dispositivo con la marca de creación `D3DCREATE_FPU_PRESERVE`. Sin esta configuración, la representación D3D puede reducir la precisión de las operaciones de precisión doble de WPF y introducir problemas de representación.  
  
 El mosaico de un <xref:System.Windows.Interop.D3DImage> es rápido, a menos que se ponga en mosaico una superficie que no sea de pow2 sin compatibilidad de hardware, o si se coloca en mosaico un <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> que contiene una <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Prácticas recomendadas para pantallas de varios monitores  
 Si utiliza un equipo que tiene varios monitores, debe seguir los procedimientos recomendados descritos anteriormente. También hay algunas consideraciones de rendimiento adicionales para una configuración de varios monitores.  
  
 Al crear el búfer de reserva, se crea en un dispositivo y adaptador específico, pero WPF puede mostrar el búfer frontal en cualquier adaptador. La copia entre adaptadores para actualizar el búfer frontal puede ser muy costosa. En Windows Vista que está configurado para usar el WDDM con varias tarjetas de vídeo y con un dispositivo `IDirect3DDevice9Ex`, si el búfer frontal está en un adaptador diferente pero sigue siendo la misma tarjeta de vídeo, no hay penalización de rendimiento. Sin embargo, en Windows XP y el XDDM con varias tarjetas de vídeo, existe una penalización significativa del rendimiento cuando el búfer frontal se muestra en un adaptador diferente del búfer de reserva. Para obtener más información, consulte [interoperabilidad de WPF y Direct3D9](wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Resumen de rendimiento  
 En la tabla siguiente se muestra el rendimiento de la actualización del búfer frontal como una función del sistema operativo, el formato de píxel y la protección de la superficie. Se supone que el búfer frontal y el búfer de reserva están en el mismo adaptador. En función de la configuración del adaptador, las actualizaciones de hardware suelen ser mucho más rápidas que las actualizaciones de software.  
  
|Formato de píxel de superficie|Windows Vista, WDDM y 9Ex|Otras configuraciones de Windows Vista|Revisión de Windows XP SP3 o SP2 con|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (no bloqueable)|**Actualización de hardware**|Actualización de software|Actualización de software|Actualización de software|  
|D3DFMT_X8R8G8B8 (bloqueable)|**Actualización de hardware**|Actualización de software|**Actualización de hardware**|**Actualización de hardware**|  
|D3DFMT_A8R8G8B8 (no bloqueable)|**Actualización de hardware**|Actualización de software|Actualización de software|Actualización de software|  
|D3DFMT_A8R8G8B8 (bloqueable)|**Actualización de hardware**|Actualización de software|**Actualización de hardware**|Actualización de software|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.D3DImage>
- [Interoperabilidad entre WPF y Direct3D9](wpf-and-direct3d9-interoperation.md)
- [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [Tutorial: Hospedar contenido Direct3D9 en WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
