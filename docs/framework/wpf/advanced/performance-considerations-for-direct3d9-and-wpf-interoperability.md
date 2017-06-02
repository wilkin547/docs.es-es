---
title: "Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9 [interoperabilidad de WPF], rendimiento"
  - "WPF, rendimiento de la interoperabilidad de Direct3D9"
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF
Puede hospedar contenido de Direct3D9 mediante la clase <xref:System.Windows.Interop.D3DImage>.  Hospedar contenido de Direct3D9 puede afectar al rendimiento de la aplicación.  En este tema se describen los procedimientos recomendados para optimizar el rendimiento cuando se hospeda contenido de Direct3D9 en una aplicación de Windows Presentation Foundation \(WPF\).  Estos procedimientos recomendados incluyen cómo utilizar <xref:System.Windows.Interop.D3DImage> y los procedimientos recomendados en entornos de Windows Vista, Windows XP y de presentaciones en varios monitores.  
  
> [!NOTE]
>  Para obtener ejemplos de código en los que se muestran estos procedimientos recomendados, vea [Interoperabilidad entre WPF y Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## Utilizar D3Dimage con moderación  
 El contenido de Direct3D9 hospedado en una instancia de <xref:System.Windows.Interop.D3DImage> no se representa tan rápido como en una aplicación de Direct3D pura.  Copiar en la superficie y vaciar el búfer de comandos son operaciones que pueden consumir muchos recursos.  A medida que aumenta el número de instancias de <xref:System.Windows.Interop.D3DImage>, más veces se efectúa el vaciado y se degrada el rendimiento.  En consecuencia, conviene utilizar <xref:System.Windows.Interop.D3DImage> con moderación.  
  
## Procedimientos recomendados en Windows Vista  
 Para obtener el máximo rendimiento en Windows Vista con una presentación configurada para utilizar el modelo de controladores de pantalla de Windows \(WDDM\), cree la superficie de Direct3D9 en un dispositivo `IDirect3DDevice9Ex`.  Esto habilita el uso compartido de la superficie.  La tarjeta de vídeo debe ser compatible con las funcionalidades de controlador `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` y `D3DCAPS2_CANSHARERESOURCE` de Windows Vista.  Cualquier otra configuración hará que la superficie se copie mediante software, lo que reduce el rendimiento de manera significativa.  
  
> [!NOTE]
>  Si Windows Vista tiene una presentación configurada para utilizar el modelo de controladores de pantalla de Windows XP \(XDDM\), la superficie siempre se copia mediante software, con independencia de la configuración.  Con la configuración y la tarjeta de vídeo apropiadas, obtendrá un rendimiento mejor en Windows Vista cuando utilice el WDDM, porque la superficie se copia mediante hardware.  
  
## Procedimientos recomendados en Windows XP  
 Para obtener el máximo rendimiento en Windows XP, que utiliza el modelo de controladores de pantalla de Windows XP \(XDDM\), cree una superficie bloqueable que se comporte correctamente cuando se llama al método `IDirect3DSurface9::GetDC`.  Internamente, el método `BitBlt` transfiere la superficie de un dispositivo de hardware a otro.  El método `GetDC` funciona siempre en las superficies XRGB.  Sin embargo, si el equipo cliente ejecuta Windows XP SP3 o SP2, y si el cliente también tiene la revisión de la característica de ventanas superpuestas, este método sólo funciona en las superficies ARGB.  La tarjeta de vídeo debe ser compatible con la funcionalidad de controlador `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES`.  
  
 Una profundidad de pantalla de escritorio de 16 bits puede reducir significativamente el rendimiento.  Se recomienda un escritorio de 32 bits.  
  
 Si está desarrollando aplicaciones para Windows Vista y Windows XP, pruebe el rendimiento en Windows XP.  Es importante evitar que se agote la memoria de vídeo en Windows XP.  Además, el objeto <xref:System.Windows.Interop.D3DImage> de Windows XP utiliza más memoria de vídeo y ancho banda que el WDDM de Windows Vista, debido a la necesidad de efectuar una copia adicional de la memoria de vídeo.  Por consiguiente, cabe esperar que el rendimiento sea peor en Windows XP que en Windows Vista para el mismo hardware de vídeo.  
  
> [!NOTE]
>  El XDDM está disponible en Windows XP y Windows Vista; sin embargo, el WDDM solo está disponible en Windows Vista.  
  
## Procedimientos recomendados generales  
 Al crear el dispositivo, utilice el marcador de creación `D3DCREATE_MULTITHREADED`.  Esto reduce el rendimiento, pero el sistema de representación de WPF llama a los métodos de este dispositivo desde otro subproceso.  Asegúrese de seguir correctamente el protocolo de bloqueo, para que no haya dos subprocesos que tengan acceso al dispositivo al mismo tiempo.  
  
 Si la representación se lleva a cabo en un subproceso administrado de WPF, se recomienda encarecidamente crear el dispositivo con el marcador de creación `D3DCREATE_FPU_PRESERVE`.  Sin este valor, la representación D3D puede reducir la exactitud de las operaciones de doble precisión de WPF y presentar problemas de representación.  
  
 Colocar en mosaico un objeto <xref:System.Windows.Interop.D3DImage> es rápido, salvo si coloca en mosaico una superficie no definida en potencias de 2 sin compatibilidad de hardware o si coloca en mosaico un objeto <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> que contiene un objeto <xref:System.Windows.Interop.D3DImage>.  
  
## Procedimientos recomendados para presentaciones en varios monitores  
 Si utiliza un equipo que tiene varios monitores, debe seguir los procedimientos recomendados descritos previamente.  Además, existen algunas consideraciones de rendimiento adicionales que deben tenerse en cuenta en las configuraciones de varios monitores.  
  
 Al crear el búfer de reserva, éste se crea en un dispositivo y adaptador concretos, pero WPF puede mostrar el búfer frontal en cualquier adaptador.  Copiar de un adaptador a otro para actualizar el búfer frontal puede consumir muchos recursos.  En un sistema Windows Vista configurado para utilizar el WDDM con varias tarjetas de vídeo y con un dispositivo `IDirect3DDevice9Ex`, si el búfer frontal se encuentra en un adaptador diferente pero pertenece a la misma tarjeta de vídeo, el rendimiento no se ve afectado.  Sin embargo, en un sistema Windows XP con el XDDM y varias tarjetas de vídeo, sí se produce una reducción del rendimiento significativa cuando el búfer frontal se muestra en un adaptador distinto al del búfer de reserva.  Para obtener más información, vea [Interoperabilidad entre WPF y Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
## Resumen de rendimiento  
 En la tabla siguiente se muestra rendimiento de la actualización del búfer frontal en función del sistema operativo, del formato de píxel y de la posibilidad de bloqueo de la superficie.  Se supone que el búfer frontal y búfer de reserva se encuentran en el mismo adaptador.  Según la configuración del adaptador, las actualizaciones de hardware suelen ser mucho más rápidas que las de software.  
  
|Formato de píxel de la superficie|Windows Vista, WDDM y 9Ex|Otras configuraciones de Windows Vista|Windows XP SP3 o SP2 con la revisión|Windows XP SP2|  
|---------------------------------------|-------------------------------|--------------------------------------------|------------------------------------------|--------------------|  
|D3DFMT\_X8R8G8B8 \(no bloqueable\)|**Actualización de hardware**|Actualización de software|Actualización de software|Actualización de software|  
|D3DFMT\_X8R8G8B8 \(bloqueable\)|**Actualización de hardware**|Actualización de software|**Actualización de hardware**|**Actualización de hardware**|  
|D3DFMT\_A8R8G8B8 \(no bloqueable\)|**Actualización de hardware**|Actualización de software|Actualización de software|Actualización de software|  
|D3DFMT\_A8R8G8B8 \(bloqueable\)|**Actualización de hardware**|Actualización de software|**Actualización de hardware**|Actualización de software|  
  
## Vea también  
 <xref:System.Windows.Interop.D3DImage>   
 [Interoperabilidad entre WPF y Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)   
 [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [Tutorial: Hospedar contenido Direct3D9 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)