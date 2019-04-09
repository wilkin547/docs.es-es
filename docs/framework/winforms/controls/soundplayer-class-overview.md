---
title: Información general sobre la clase SoundPlayer
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195012"
---
# <a name="soundplayer-class-overview"></a>Información general sobre la clase SoundPlayer
La clase <xref:System.Media.SoundPlayer> le permite incluir con facilidad sonidos en las aplicaciones.  
  
 La <xref:System.Media.SoundPlayer> clase puede reproducir archivos de sonido en formato .wav desde un recurso o desde ubicaciones HTTP o UNC. Además, el <xref:System.Media.SoundPlayer> clase le permite cargar o reproducir sonidos de forma asincrónica.  
  
 También puede utilizar la clase <xref:System.Media.SystemSounds> para reproducir sonidos de sistema comunes, incluso un bip.   
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades, métodos y eventos de uso común  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> propiedad|Ruta de acceso del archivo o dirección web del sonido. Los valores admitidos pueden ser UNC o HTTP.|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> propiedad|Número de milisegundos que el programa esperará para cargar un sonido antes de iniciar una excepción. El valor predeterminado es 10 segundos.|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> propiedad|Valor booleano que indica si el sonido finalizó la carga.|  
|<xref:System.Media.SoundPlayer.Load%2A> método|Carga un sonido de forma sincrónica.|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> método|Comienza a cargar un sonido de forma asincrónica. Una vez completada la carga, genera el <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> eventos.|  
|<xref:System.Media.SoundPlayer.Play%2A> método|Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en un nuevo subproceso.|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> método|Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en el subproceso actual.|  
|<xref:System.Media.SoundPlayer.Stop%2A> método|Detiene cualquier sonido que se esté reproduciendo.|  
|<xref:System.Media.SoundPlayer.LoadCompleted> evento|Se genera después de que se intente cargar un sonido.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
