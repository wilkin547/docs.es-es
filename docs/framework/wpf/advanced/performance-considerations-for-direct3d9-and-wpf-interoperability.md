---
title: Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 1371fa901bebc503a0091f3229a8fd7e6ccc2c86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772858"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF
Puede hospedar contenido Direct3D9 mediante la <xref:System.Windows.Interop.D3DImage> clase. Hospedar contenido Direct3D9 puede afectar al rendimiento de la aplicación. En este tema se describe los procedimientos recomendados para optimizar el rendimiento al hospedar contenido Direct3D9 en una aplicación de Windows Presentation Foundation (WPF). Estas recomendaciones incluyen cómo usar <xref:System.Windows.Interop.D3DImage> y procedimientos recomendados cuando usa Windows Vista, Windows XP, y se muestran varios monitores.  
  
> [!NOTE]
>  Para obtener ejemplos de código que muestran estos procedimientos recomendados, consulte [interoperabilidad entre Direct3D9 y WPF](wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Utilice con moderación D3DImage  
 Contenido Direct3D9 hospedado en un <xref:System.Windows.Interop.D3DImage> instancia no se representará tan rápido como en una aplicación de Direct3D pura. Copiar en la superficie y vaciar el búfer de comandos pueden ser operaciones costosas. Como el número de <xref:System.Windows.Interop.D3DImage> aumenta las instancias, más el vaciado se produce y degrada el rendimiento. Por lo tanto, debe usar <xref:System.Windows.Interop.D3DImage> con moderación.  
  
## <a name="best-practices-on-windows-vista"></a>Procedimientos recomendados en Windows Vista  
 Para optimizar el rendimiento de Windows Vista con una visualización que está configurado para usar el modelo de controladores de pantalla de Windows (WDDM), cree la superficie de Direct3D9 en un `IDirect3DDevice9Ex` dispositivo. Esto permite el uso compartido de superficie. La tarjeta de vídeo debe admitir la `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` y `D3DCAPS2_CANSHARERESOURCE` funciones del controlador en Windows Vista. Cualquier otra configuración hará que la superficie que se va a copiar a través de software, lo que reduce significativamente el rendimiento.  
  
> [!NOTE]
>  Si Windows Vista tiene una presentación que está configurada para usar el Windows XP Mostrar controladores modelo (XDDM), la superficie siempre se copia a través de software, independientemente de la configuración. Con las opciones adecuadas y la tarjeta de vídeo, verá un mejor rendimiento en Windows Vista cuando se usa el WDDM porque se realizan copias de superficie en hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Procedimientos recomendados en Windows XP  
 Para obtener el mejor rendimiento en Windows XP, que usa el modelo de controladores de pantalla de Windows XP (XDDM), cree una superficie bloqueable que se comporta correctamente cuando el `IDirect3DSurface9::GetDC` se llama al método. Internamente, el `BitBlt` método transfiere la superficie en dispositivos de hardware. El `GetDC` método siempre funciona en las superficies XRGB. Sin embargo, si el equipo cliente ejecuta Windows XP con SP3 o SP2, y si el cliente también tiene la revisión de la característica de ventana por capas, este método solo funciona en las superficies ARGB. La tarjeta de vídeo debe admitir la `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` funcionalidad del controlador.  
  
 Una profundidad de la pantalla del escritorio de 16 bits puede reducir significativamente el rendimiento. Se recomienda un escritorio de 32 bits.  
  
 Si está desarrollando para Windows Vista y Windows XP, pruebe el rendimiento de Windows XP. Quedarse sin memoria de vídeo en Windows XP es una preocupación. Además, <xref:System.Windows.Interop.D3DImage> en Windows XP usa más memoria de vídeo y ancho de banda que Windows Vista WDDM, debido a una copia en memoria de vídeo adicionales necesarios. Por lo tanto, puede esperar un rendimiento peor en Windows XP que en Windows Vista sea el mismo hardware de vídeo.  
  
> [!NOTE]
>  XDDM está disponible en Windows XP y Windows Vista; Sin embargo, WDDM solo está disponible en Windows Vista.  
  
## <a name="general-best-practices"></a>Procedimientos recomendados generales  
 Cuando se crea el dispositivo, use el `D3DCREATE_MULTITHREADED` indicador de creación. Esto reduce el rendimiento, pero el sistema de representación de WPF llama a métodos en este dispositivo desde otro subproceso. Asegúrese de seguir correctamente, el protocolo de bloqueo para que no haya dos subprocesos acceda al dispositivo al mismo tiempo.  
  
 Si la representación se realiza en un subproceso administrado de WPF, se recomienda encarecidamente que cree el dispositivo con el `D3DCREATE_FPU_PRESERVE` indicador de creación. Sin esta configuración, la representación D3D puede reducir la precisión de las operaciones de doble precisión WPF y presentar problemas de representación.  
  
 Disposición en mosaico una <xref:System.Windows.Interop.D3DImage> es rápido, a menos que se coloca en mosaico una superficie no pow2 sin compatibilidad de hardware, o si coloca en mosaico una <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> que contiene un <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Procedimientos recomendados para las pantallas de varios monitores  
 Si usas un equipo que tiene varios monitores, debe seguir los procedimientos recomendados descritos anteriormente. También hay algunas consideraciones de rendimiento adicionales para una configuración de varios monitor.  
  
 Al crear el búfer de reserva, se crea en un dispositivo específico y el adaptador pero WPF puede mostrar el búfer frontal en ningún adaptador. Copiar en todos los adaptadores para actualizar el búfer frontal puede resultar muy caro. En Windows Vista que está configurado para utilizar el WDDM con varias tarjetas de vídeo y con un `IDirect3DDevice9Ex` dispositivo, si el búfer frontal es en un adaptador diferente pero la misma tarjeta de vídeo, no hay ninguna reducción del rendimiento. Sin embargo, en Windows XP y el XDDM con varias tarjetas de vídeo, hay una importante penalización del rendimiento cuando el búfer frontal se muestra en un adaptador distinto al búfer de reserva. Para obtener más información, consulte [interoperabilidad entre Direct3D9 y WPF](wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Resumen de rendimiento  
 En la tabla siguiente se muestra el rendimiento de la actualización de búfer frontal como una función de sistema operativo, el formato de píxel y posibilidad de bloqueo de superficie. El búfer frontal y el búfer de reserva se supone que en el mismo adaptador. Dependiendo de la configuración del adaptador, las actualizaciones de hardware son generalmente mucho más rápidas que las actualizaciones de software.  
  
|Formato de píxel de la superficie|Windows Vista, WDDM y 9Ex|Otras configuraciones de Windows Vista|Windows XP SP3 o SP2 con la revisión|Windows XP SP2|  
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
