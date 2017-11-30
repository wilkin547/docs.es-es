---
title: Reproducir sonidos (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8be5cec634482bf99ddff4ff6b6af8e897c4909e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="131da-102">Reproducir sonidos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131da-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="131da-103">El objeto `My.Computer.Audio` proporciona métodos para reproducir sonidos.</span><span class="sxs-lookup"><span data-stu-id="131da-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="131da-104">Reproducir sonidos</span><span class="sxs-lookup"><span data-stu-id="131da-104">Playing Sounds</span></span>  
 <span data-ttu-id="131da-105">La reproducción en segundo plano permite que la aplicación ejecute otro código mientras se reproduce el sonido.</span><span class="sxs-lookup"><span data-stu-id="131da-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="131da-106">El método `My.Computer.Audio.Play` permite que la aplicación solo reproduzca un sonido de fondo a la vez; cuando la aplicación reproduce un nuevo sonido de fondo, detiene la reproducción del sonido anterior.</span><span class="sxs-lookup"><span data-stu-id="131da-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="131da-107">También puede reproducir un sonido y esperar a que finalice.</span><span class="sxs-lookup"><span data-stu-id="131da-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="131da-108">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce un sonido.</span><span class="sxs-lookup"><span data-stu-id="131da-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="131da-109">Cuando se especifica `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` espera a que el sonido finalice antes de seguir con el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="131da-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="131da-110">Cuando use este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav en su equipo.</span><span class="sxs-lookup"><span data-stu-id="131da-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]  
  
 <span data-ttu-id="131da-111">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce un sonido.</span><span class="sxs-lookup"><span data-stu-id="131da-111">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="131da-112">Cuando use este ejemplo, debe asegurarse de que los recursos de aplicación incluyen un archivo de sonido .wav denominado Cascada.</span><span class="sxs-lookup"><span data-stu-id="131da-112">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="131da-113">Reproducción de sonidos en bucle</span><span class="sxs-lookup"><span data-stu-id="131da-113">Playing Looping Sounds</span></span>  
 <span data-ttu-id="131da-114">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano al especificar `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="131da-114">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="131da-115">Cuando use este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav en su equipo.</span><span class="sxs-lookup"><span data-stu-id="131da-115">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]  
  
 <span data-ttu-id="131da-116">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano al especificar `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="131da-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="131da-117">Cuando use este ejemplo, debe asegurarse de que los recursos de aplicación incluyen un archivo de sonido .wav denominado Cascada.</span><span class="sxs-lookup"><span data-stu-id="131da-117">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]  
  
 <span data-ttu-id="131da-118">El ejemplo de código anterior también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="131da-118">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="131da-119">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Sonido**.</span><span class="sxs-lookup"><span data-stu-id="131da-119">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="131da-120">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="131da-120">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="131da-121">En general, cuando una aplicación reproduce un sonido en bucle, al final hay que detener el sonido.</span><span class="sxs-lookup"><span data-stu-id="131da-121">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="131da-122">Detención de la reproducción de sonidos en segundo plano</span><span class="sxs-lookup"><span data-stu-id="131da-122">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="131da-123">Use el método `My.Computer.Audio.Stop` para detener el sonido de fondo o en bucle que la aplicación reproduce.</span><span class="sxs-lookup"><span data-stu-id="131da-123">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="131da-124">En general, cuando una aplicación reproduce un sonido en bucle, en algún momento hay que detener el sonido.</span><span class="sxs-lookup"><span data-stu-id="131da-124">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="131da-125">En el ejemplo siguiente se detiene un sonido que se reproduce en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="131da-125">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]  
  
 <span data-ttu-id="131da-126">El ejemplo de código anterior también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="131da-126">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="131da-127">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Sonido**.</span><span class="sxs-lookup"><span data-stu-id="131da-127">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="131da-128">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="131da-128">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="131da-129">Reproducción de sonidos del sistema</span><span class="sxs-lookup"><span data-stu-id="131da-129">Playing System Sounds</span></span>  
 <span data-ttu-id="131da-130">Use el método `My.Computer.Audio.PlaySystemSound` para reproducir el sonido del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="131da-130">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="131da-131">El método `My.Computer.Audio.PlaySystemSound` toma como parámetro uno de los miembros compartidos de la clase <xref:System.Media.SystemSound>.</span><span class="sxs-lookup"><span data-stu-id="131da-131">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="131da-132">La propiedad <xref:System.Media.SystemSounds.Asterisk%2A> en el sonido del sistema generalmente denota errores.</span><span class="sxs-lookup"><span data-stu-id="131da-132">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="131da-133">En el ejemplo siguiente se usa el método `My.Computer.Audio.PlaySystemSound` para reproducir un sonido del sistema.</span><span class="sxs-lookup"><span data-stu-id="131da-133">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="131da-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="131da-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>  
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>  
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>  
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>  
 <xref:Microsoft.VisualBasic.AudioPlayMode>
