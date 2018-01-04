---
title: "Información general sobre la clase SoundPlayer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dc355fbe0d8262cb24779b99375d6075f758bbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="soundplayer-class-overview"></a>Información general sobre la clase SoundPlayer
La clase <xref:System.Media.SoundPlayer> le permite incluir con facilidad sonidos en las aplicaciones.  
  
 La <xref:System.Media.SoundPlayer> clase puede reproducir archivos de sonido en el formato .wav, desde un recurso o desde ubicaciones HTTP o UNC. Además, la <xref:System.Media.SoundPlayer> clase le permite cargar o reproducir sonidos de forma asincrónica.  
  
 También puede utilizar la clase <xref:System.Media.SystemSounds> para reproducir sonidos de sistema comunes, incluso un bip.   
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades, métodos y eventos de uso común  
  
|nombre|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Media.SoundPlayer.SoundLocation%2A>|Ruta de acceso del archivo o dirección web del sonido. Los valores admitidos pueden ser UNC o HTTP.|  
|Propiedad <xref:System.Media.SoundPlayer.LoadTimeout%2A>|Número de milisegundos que el programa esperará para cargar un sonido antes de iniciar una excepción. El valor predeterminado es 10 segundos.|  
|Propiedad <xref:System.Media.SoundPlayer.IsLoadCompleted%2A>|Valor booleano que indica si el sonido finalizó la carga.|  
|Método <xref:System.Media.SoundPlayer.Load%2A>|Carga un sonido de forma sincrónica.|  
|Método <xref:System.Media.SoundPlayer.LoadAsync%2A>|Comienza a cargar un sonido de forma asincrónica. Una vez completada la carga, genera el <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> eventos.|  
|Método <xref:System.Media.SoundPlayer.Play%2A>|Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en un nuevo subproceso.|  
|Método <xref:System.Media.SoundPlayer.PlaySync%2A>|Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en el subproceso actual.|  
|Método <xref:System.Media.SoundPlayer.Stop%2A>|Detiene cualquier sonido que se esté reproduciendo.|  
|Evento <xref:System.Media.SoundPlayer.LoadCompleted>|Se genera después de que se intente cargar un sonido.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
