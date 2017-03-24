---
title: "Reproducir sonidos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Audio (objeto), tareas"
  - "reproducir sonidos"
  - "reproducir sonidos, Visual Basic"
  - "bucles de sonido"
  - "sonidos, fondo"
  - "sonidos, reproducir"
  - "sonidos del sistema"
  - "sonidos del sistema, reproducir"
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Reproducir sonidos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto `My.Computer.Audio` proporciona los métodos para reproducir sonidos.  
  
## Reproducir sonidos  
 La reproducción en segundo plano permite que la aplicación ejecute otro código mientras se reproduce el sonido.  El método `My.Computer.Audio.Play` permite que la aplicación reproduzca solo un sonido de fondo a la vez; cuando la aplicación reproduce un nuevo sonido de fondo, deja de reproducir el sonido de fondo anterior.  También se puede reproducir un sonido y esperar a que se complete.  
  
 En el ejemplo siguiente, el método de `My.Computer.Audio.Play` reproduce un sonido.  Cuando se especifica `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` espera hasta que el sonido se completa antes de que el código de llamada continúe.  Al utilizar este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav que está en el equipo  
  
 [!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]  
  
 En el ejemplo siguiente, el método de `My.Computer.Audio.Play` reproduce un sonido.  Al utilizar este ejemplo, debe asegurarse de que los recursos de la aplicación incluyen un archivo de sonido .wav denominado Waterfall.  
  
 [!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]  
  
## Reproducir sonidos de Bucle  
 En el ejemplo siguiente, el método de `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano cuando se especifica `PlayMode.BackgroundLoop` .  Al utilizar este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav que está en el equipo.  
  
 [!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]  
  
 En el ejemplo siguiente, el método de `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano cuando se especifica `PlayMode.BackgroundLoop` .  Al utilizar este ejemplo, debe asegurarse de que los recursos de la aplicación incluyen un archivo de sonido .wav denominado Waterfall.  
  
 [!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]  
  
 El ejemplo de código anterior también está disponible como fragmentos de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms \> Sonido**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
 En general, cuando una aplicación repite un bucle de sonido, debe detener el sonido en algún momento.  
  
## Detiene la reproducción del sonido en segundo plano  
 Utilice el método `My.Computer.Audio.Stop` para detener la reproducción del sonido en segundo plano o en bucle de repetición que está reproduciendo actualmente la aplicación.  
  
 En general, cuando una aplicación reproduce un sonido en bucle de repetición, debería detener el sonido en algún momento dado.  
  
 El ejemplo siguiente se detiene un sonido que se está reproduciendo en segundo plano.  
  
 [!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]  
  
 El ejemplo de código anterior también está disponible como fragmentos de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms \> Sonido**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Reproducir sonidos de sistema  
 Utilice el método `My.Computer.Audio.PlaySystemSound` para reproducir el sonido del sistema especificado.  
  
 El método `My.Computer.Audio.PlaySystemSound` toma como parámetro uno de los miembros compartidos de la clase <xref:System.Media.SystemSound>.  El sonido del sistema <xref:System.Media.SystemSounds.Asterisk%2A> generalmente denota errores.  
  
 El ejemplo siguiente se usa el método de `My.Computer.Audio.PlaySystemSound` para reproducir un sonido del sistema.  
  
 [!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>