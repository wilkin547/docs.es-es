---
title: Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: 52085579c2a432e7db1ebec096a931e0d51718f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549209"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF
Puede hospedar contenido de Direct3D9 mediante la <xref:System.Windows.Interop.D3DImage> clase. Hospedar contenido de Direct3D9 puede afectar al rendimiento de la aplicación. En este tema se describe las prácticas recomendadas para optimizar el rendimiento al hospedar contenido de Direct3D9 en una aplicación de Windows Presentation Foundation (WPF). Estas prácticas recomendadas incluyen cómo utilizar <xref:System.Windows.Interop.D3DImage> y las prácticas recomendadas cuando está utilizando Windows Vista, Windows XP, y muestra varios monitores.  
  
> [!NOTE]
>  Para obtener ejemplos de código que muestran estas prácticas recomendadas, consulte [WPF y Direct3D9 interoperación](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## <a name="use-d3dimage-sparingly"></a>Utilizar D3DImage con moderación  
 Contenido de Direct3D9 hospedado en un <xref:System.Windows.Interop.D3DImage> instancia no se representa tan rápido como en una aplicación de Direct3D pura. Copiar en la superficie y vaciar el búfer de comandos pueden ser operaciones costosas. Como el número de <xref:System.Windows.Interop.D3DImage> aumenta de instancias, más baja se produce y degrada el rendimiento. Por lo tanto, debe usar <xref:System.Windows.Interop.D3DImage> con moderación.  
  
## <a name="best-practices-on-windows-vista"></a>Procedimientos recomendados en Windows Vista  
 Para obtener el mejor rendimiento en Windows Vista con una presentación que está configurado para usar el modelo de controlador de pantalla de Windows (WDDM), debe crear la superficie de Direct3D9 en un `IDirect3DDevice9Ex` dispositivo. Esto permite compartir expuesta. La tarjeta de vídeo debe admitir la `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` y `D3DCAPS2_CANSHARERESOURCE` funciones del controlador en Windows Vista. Cualquier otra configuración hará que la superficie que se copiará a través del software, lo que reduce significativamente el rendimiento.  
  
> [!NOTE]
>  Si Windows Vista tiene una presentación que está configurada para usar el modelo Windows XP Mostrar controlador (XDDM), la superficie siempre se copia a través de software, independientemente de la configuración. Con las opciones adecuadas y la tarjeta de vídeo, verá un mejor rendimiento en Windows Vista cuando se usa el WDDM porque se realizan copias de superficie en hardware.  
  
## <a name="best-practices-on-windows-xp"></a>Procedimientos recomendados en Windows XP  
 Para obtener el mejor rendimiento en Windows XP, que usa el modelo de controlador de pantalla de Windows XP (XDDM), cree una superficie bloqueable que se comporta correctamente cuando el `IDirect3DSurface9::GetDC` se llama al método. Internamente, la `BitBlt` método transfiere la superficie en todos los dispositivos de hardware. El `GetDC` método siempre funciona en las superficies XRGB. Sin embargo, si el equipo cliente ejecuta Windows XP con SP3 o SP2, y si el cliente también tiene la revisión de la característica de ventana en capas, este método solo funciona en las superficies ARGB. La tarjeta de vídeo debe admitir la `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` capacidad de controlador.  
  
 Una profundidad de visualización de escritorio de 16 bits puede reducir significativamente el rendimiento. Se recomienda un escritorio de 32 bits.  
  
 Si va a desarrollar para Windows Vista y Windows XP, pruebe el rendimiento en Windows XP. Quedarse sin memoria de vídeo en Windows XP es una preocupación. Además, <xref:System.Windows.Interop.D3DImage> en Windows XP usa más memoria de vídeo y ancho de banda que Windows Vista WDDM, debido a una copia de memoria de vídeo adicional es necesario. Por lo tanto, puede esperar un rendimiento sea peor en Windows XP que en Windows Vista para el mismo hardware de vídeo.  
  
> [!NOTE]
>  XDDM está disponible en Windows XP y Windows Vista; Sin embargo, WDDM solo está disponible en Windows Vista.  
  
## <a name="general-best-practices"></a>Procedimientos recomendados generales  
 Cuando se crea el dispositivo, use la `D3DCREATE_MULTITHREADED` indicador de creación. Esto reduce el rendimiento, pero el sistema de representación de WPF llama a métodos en este dispositivo desde otro subproceso. Asegúrese de seguir el protocolo de bloqueo correctamente, por lo que no haya dos subprocesos acceda al dispositivo al mismo tiempo.  
  
 Si la representación se realiza en un subproceso administrado de WPF, se recomienda encarecidamente que cree el dispositivo con el `D3DCREATE_FPU_PRESERVE` indicador de creación. Sin esta configuración, la representación D3D puede reducir la exactitud de las operaciones de doble precisión WPF y presentar problemas de representación.  
  
 Disponer en mosaico un <xref:System.Windows.Interop.D3DImage> es rápido, a menos que se coloca en mosaico una superficie no pow2 sin compatibilidad con el hardware o si coloca en mosaico una <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> que contiene un <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>Procedimientos recomendados para presentaciones en varios monitores  
 Si está usando un equipo que tiene varios monitores, debe seguir los procedimientos recomendados descritos anteriormente. También hay algunas consideraciones de rendimiento adicionales para una configuración de varios monitor.  
  
 Cuando se crea el búfer de reserva, se crea en un dispositivo específico y el adaptador, pero WPF puede mostrar el búfer frontal en ningún adaptador. Copiar a través de adaptadores que se va a actualizar el búfer frontal puede resultar muy caro. En Windows Vista que está configurado para utilizar el WDDM con varias tarjetas de vídeo y con un `IDirect3DDevice9Ex` dispositivo, si el búfer frontal se encuentra en un adaptador diferente pero la misma tarjeta de vídeo, no hay ninguna reducción del rendimiento. Sin embargo, en Windows XP y el XDDM con varias tarjetas de vídeo, hay una reducción del rendimiento significativa cuando el búfer frontal se muestra en un adaptador distinto que el búfer de reserva. Para obtener más información, consulte [WPF y Direct3D9 interoperación](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## <a name="performance-summary"></a>Resumen de rendimiento  
 La siguiente tabla muestra el rendimiento de la actualización del búfer frontal como una función de sistema operativo, el formato de píxel y posibilidad de bloqueo de superficie. El búfer frontal y búfer de reserva se supone que en el mismo adaptador. Dependiendo de la configuración del adaptador, las actualizaciones de hardware son generalmente mucho más rápidas que las actualizaciones de software.  
  
|Formato de píxel de la superficie|Windows Vista, WDDM y 9Ex|Otras configuraciones de Windows Vista|Windows XP SP3 o SP2 con la revisión|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (no bloqueable)|**Actualización de hardware**|Actualización de software|Actualización de software|Actualización de software|  
|D3DFMT_X8R8G8B8 (bloqueable)|**Actualización de hardware**|Actualización de software|**Actualización de hardware**|**Actualización de hardware**|  
|D3DFMT_A8R8G8B8 (no bloqueable)|**Actualización de hardware**|Actualización de software|Actualización de software|Actualización de software|  
|D3DFMT_A8R8G8B8 (bloqueable)|**Actualización de hardware**|Actualización de software|**Actualización de hardware**|Actualización de software|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Interop.D3DImage>  
 [Interoperabilidad entre WPF y Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)  
 [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [Tutorial: Hospedar contenido Direct3D9 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
