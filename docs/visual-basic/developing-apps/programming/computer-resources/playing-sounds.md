---
title: Reproducir sonidos (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a15efff54bd54fdaced6c741cd6acf5c8b544cdd
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="6d3d7-102">Reproducir sonidos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d3d7-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="6d3d7-103">El objeto `My.Computer.Audio` proporciona métodos para reproducir sonidos.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="6d3d7-104">Reproducir sonidos</span><span class="sxs-lookup"><span data-stu-id="6d3d7-104">Playing Sounds</span></span>  
 <span data-ttu-id="6d3d7-105">La reproducción en segundo plano permite que la aplicación ejecute otro código mientras se reproduce el sonido.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="6d3d7-106">El método `My.Computer.Audio.Play` permite que la aplicación solo reproduzca un sonido de fondo a la vez; cuando la aplicación reproduce un nuevo sonido de fondo, detiene la reproducción del sonido anterior.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="6d3d7-107">También puede reproducir un sonido y esperar a que finalice.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="6d3d7-108">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce un sonido.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="6d3d7-109">Cuando se especifica `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` espera a que el sonido finalice antes de seguir con el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="6d3d7-110">Cuando use este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 <span data-ttu-id="6d3d7-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6d3d7-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span></span>  
  
 <span data-ttu-id="6d3d7-112">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce un sonido.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="6d3d7-113">Cuando use este ejemplo, debe asegurarse de que los recursos de aplicación incluyen un archivo de sonido .wav denominado Cascada.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="6d3d7-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="6d3d7-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span></span>  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="6d3d7-115">Reproducción de sonidos en bucle</span><span class="sxs-lookup"><span data-stu-id="6d3d7-115">Playing Looping Sounds</span></span>  
 <span data-ttu-id="6d3d7-116">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano al especificar `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="6d3d7-117">Cuando use este ejemplo, debe asegurarse de que el nombre de archivo hace referencia a un archivo de sonido .wav en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-117">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 <span data-ttu-id="6d3d7-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="6d3d7-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span></span>  
  
 <span data-ttu-id="6d3d7-119">En el ejemplo siguiente, el método `My.Computer.Audio.Play` reproduce el sonido especificado en segundo plano al especificar `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-119">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="6d3d7-120">Cuando use este ejemplo, debe asegurarse de que los recursos de aplicación incluyen un archivo de sonido .wav denominado Cascada.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-120">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="6d3d7-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="6d3d7-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span></span>  
  
 <span data-ttu-id="6d3d7-122">El ejemplo de código anterior también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-122">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="6d3d7-123">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Sonido**.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-123">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="6d3d7-124">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="6d3d7-124">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="6d3d7-125">En general, cuando una aplicación reproduce un sonido en bucle, al final hay que detener el sonido.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-125">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="6d3d7-126">Detención de la reproducción de sonidos en segundo plano</span><span class="sxs-lookup"><span data-stu-id="6d3d7-126">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="6d3d7-127">Use el método `My.Computer.Audio.Stop` para detener el sonido de fondo o en bucle que la aplicación reproduce.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-127">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="6d3d7-128">En general, cuando una aplicación reproduce un sonido en bucle, en algún momento hay que detener el sonido.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-128">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="6d3d7-129">En el ejemplo siguiente se detiene un sonido que se reproduce en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-129">The following example stops a sound that is playing in the background.</span></span>  
  
 <span data-ttu-id="6d3d7-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="6d3d7-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span></span>  
  
 <span data-ttu-id="6d3d7-131">El ejemplo de código anterior también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-131">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="6d3d7-132">En el selector de fragmentos de código, se encuentra en **Aplicaciones de Windows Forms > Sonido**.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-132">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="6d3d7-133">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="6d3d7-133">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="6d3d7-134">Reproducción de sonidos del sistema</span><span class="sxs-lookup"><span data-stu-id="6d3d7-134">Playing System Sounds</span></span>  
 <span data-ttu-id="6d3d7-135">Use el método `My.Computer.Audio.PlaySystemSound` para reproducir el sonido del sistema especificado.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-135">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="6d3d7-136">El método `My.Computer.Audio.PlaySystemSound` toma como parámetro uno de los miembros compartidos de la clase <xref:System.Media.SystemSound>.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-136">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="6d3d7-137">La propiedad <xref:System.Media.SystemSounds.Asterisk%2A> en el sonido del sistema generalmente denota errores.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-137">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="6d3d7-138">En el ejemplo siguiente se usa el método `My.Computer.Audio.PlaySystemSound` para reproducir un sonido del sistema.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-138">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 <span data-ttu-id="6d3d7-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="6d3d7-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3d7-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d3d7-140">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>

