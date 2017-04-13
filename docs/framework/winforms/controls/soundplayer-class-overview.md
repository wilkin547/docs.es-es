---
title: "Informaci&#243;n general sobre la clase SoundPlayer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "reproducir sonidos, SoundPlayer (clase)"
  - "SoundPlayer (clase), acerca de la clase SoundPlayer"
  - "sonidos, reproducción"
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre la clase SoundPlayer
El <xref:System.Media.SoundPlayer> clase le permite incluir con facilidad sonidos en las aplicaciones.  
  
 El <xref:System.Media.SoundPlayer> clase puede reproducir archivos de sonido en formato .wav desde un recurso o desde ubicaciones HTTP o UNC. Además, el <xref:System.Media.SoundPlayer> clase le permite cargar o reproducir sonidos de forma asincrónica.  
  
 También puede utilizar el <xref:System.Media.SystemSounds> clase para reproducir sonidos de sistema comunes, incluso un bip.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Propiedades utilizadas con frecuencia, métodos y eventos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> propiedad|La ruta de acceso de archivo o dirección Web del sonido. Valores admitidos pueden ser UNC o HTTP.|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> propiedad|El número de milisegundos que su programa esperará para cargar un sonido antes de que produce una excepción. El valor predeterminado es 10 segundos.|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> propiedad|Un valor booleano que indica si el sonido ha terminado de cargarse.|  
|<xref:System.Media.SoundPlayer.Load%2A> (método)|Carga un sonido de forma sincrónica.|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> (método)|Comienza a cargar un sonido de forma asincrónica. Una vez finalizada la carga, provoca la <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> eventos.|  
|<xref:System.Media.SoundPlayer.Play%2A> (método)|Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en un nuevo subproceso.|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> (método)|Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en el subproceso actual.|  
|<xref:System.Media.SoundPlayer.Stop%2A> (método)|Se detiene cualquier sonido que se está reproduciendo.|  
|<xref:System.Media.SoundPlayer.LoadCompleted> eventos|Se desencadena después de que se intente realizar la carga de un sonido.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>