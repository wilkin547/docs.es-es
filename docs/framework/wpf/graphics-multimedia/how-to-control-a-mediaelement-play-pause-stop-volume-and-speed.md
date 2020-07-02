---
title: 'Cómo: Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)'
description: Controlar la reproducción de elementos multimedia en Windows Presentation Foundation (WPF). Iniciar, detener, pausar, saltar atrás y ajustar el volumen y la velocidad.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853604"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="03d27-104">Cómo: Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)</span><span class="sxs-lookup"><span data-stu-id="03d27-104">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="03d27-105">En el ejemplo siguiente se muestra cómo controlar la reproducción de medios mediante <xref:System.Windows.Controls.MediaElement> .</span><span class="sxs-lookup"><span data-stu-id="03d27-105">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="03d27-106">En el ejemplo se crea un reproductor multimedia sencillo que permite reproducir, pausar, detener y saltar hacia atrás y hacia delante en el medio, así como ajustar el volumen y la proporción de velocidad.</span><span class="sxs-lookup"><span data-stu-id="03d27-106">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03d27-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03d27-107">Example</span></span>  
 <span data-ttu-id="03d27-108">El código siguiente crea la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="03d27-108">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03d27-109">La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedad de <xref:System.Windows.Controls.MediaElement> debe establecerse en para poder `Manual` detener, pausar y reproducir los medios interactivamente.</span><span class="sxs-lookup"><span data-stu-id="03d27-109">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="03d27-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03d27-110">Example</span></span>  
 <span data-ttu-id="03d27-111">El código siguiente implementa la funcionalidad de los controles de interfaz de usuario de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03d27-111">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="03d27-112">Los <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A> métodos, y <xref:System.Windows.Controls.MediaElement.Stop%2A> se usan para reproducir, pausar y detener el medio respectivamente.</span><span class="sxs-lookup"><span data-stu-id="03d27-112">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="03d27-113">Cambiar la <xref:System.Windows.Controls.MediaElement.Position%2A> propiedad de <xref:System.Windows.Controls.MediaElement> le permite omitir el contenido multimedia.</span><span class="sxs-lookup"><span data-stu-id="03d27-113">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="03d27-114">Por último, <xref:System.Windows.Controls.MediaElement.Volume%2A> las <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> propiedades y se usan para ajustar el volumen y la velocidad de reproducción del medio.</span><span class="sxs-lookup"><span data-stu-id="03d27-114">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="03d27-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="03d27-115">See also</span></span>

- [<span data-ttu-id="03d27-116">Controlar un control MediaElement mediante un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="03d27-116">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
