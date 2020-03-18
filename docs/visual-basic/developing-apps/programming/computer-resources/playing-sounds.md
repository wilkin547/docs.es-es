---
title: Reproducir sonidos
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: 416fedd011ff35d2b32d1b64932e3908a73ed14e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345519"
---
# <a name="playing-sounds-visual-basic"></a>Reproducir sonidos (Visual Basic)

El objeto `My.Computer.Audio` proporciona métodos para reproducir sonidos.  
  
## <a name="playing-sounds"></a>Reproducir sonidos  

 La reproducción en segundo plano permite que la aplicación ejecute otro código mientras se reproduce el sonido. El método `My.Computer.Audio.Play` permite que la aplicación solo reproduzca un sonido de fondo a la vez; cuando la aplicación reproduce un nuevo sonido de fondo, detiene la reproducción del sonido anterior. También puede reproducir un sonido y esperar a que finalice.  
  
 En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce un sonido. Cuando se especifica `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` espera a que el sonido finalice antes de seguir con el código de llamada. Cuando use este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav en su equipo.  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce un sonido. Cuando use este ejemplo, debe asegurarse de que los recursos de aplicación incluyen un archivo de sonido .wav denominado Cascada.  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a>Reproducción de sonidos en bucle  

 En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano al especificar `PlayMode.BackgroundLoop`. Cuando use este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav en su equipo.  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano al especificar `PlayMode.BackgroundLoop`. Cuando use este ejemplo, debe asegurarse de que los recursos de aplicación incluyen un archivo de sonido .wav denominado Cascada.  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 El ejemplo de código anterior también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Sonido**. Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).  
  
 En general, cuando una aplicación reproduce un sonido en bucle, al final hay que detener el sonido.  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a>Detención de la reproducción de sonidos en segundo plano  

 Use el método `My.Computer.Audio.Stop` para detener el sonido de fondo o en bucle que la aplicación reproduce.  
  
 En general, cuando una aplicación reproduce un sonido en bucle, en algún momento hay que detener el sonido.  
  
 En el ejemplo siguiente se detiene un sonido que se reproduce en segundo plano.  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 El ejemplo de código anterior también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Sonido**. Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).  
  
## <a name="playing-system-sounds"></a>Reproducción de sonidos del sistema  

 Use el método `My.Computer.Audio.PlaySystemSound` para reproducir el sonido del sistema especificado.  
  
 El método `My.Computer.Audio.PlaySystemSound` toma como parámetro uno de los miembros compartidos de la clase <xref:System.Media.SystemSound>. La propiedad <xref:System.Media.SystemSounds.Asterisk%2A> en el sonido del sistema generalmente denota errores.  
  
 En el ejemplo siguiente se usa el método `My.Computer.Audio.PlaySystemSound` para reproducir un sonido del sistema.  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
