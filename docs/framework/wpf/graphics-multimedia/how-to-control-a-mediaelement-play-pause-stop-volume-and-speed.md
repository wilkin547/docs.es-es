---
title: Procedimiento Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)
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
ms.openlocfilehash: 7fe8107f7b5b65f00f2c5ac029f806aeba758d20
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368511"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="766d2-102">Filtrar Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)</span><span class="sxs-lookup"><span data-stu-id="766d2-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="766d2-103">El ejemplo siguiente muestra cómo controlar la reproducción de medios mediante un <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="766d2-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="766d2-104">El ejemplo crea un Reproductor de medios sencillo que permite reproducir, pausar, detener y avanzar o retroceder en el medio así como ajustar la proporción de volumen y velocidad.</span><span class="sxs-lookup"><span data-stu-id="766d2-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="766d2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="766d2-105">Example</span></span>  
 <span data-ttu-id="766d2-106">El código siguiente crea la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="766d2-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="766d2-107">El <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedad de <xref:System.Windows.Controls.MediaElement> debe establecerse en `Manual` para poder detener de forma interactiva, pausar y reproducir el archivo multimedia.</span><span class="sxs-lookup"><span data-stu-id="766d2-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="766d2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="766d2-108">Example</span></span>  
 <span data-ttu-id="766d2-109">El código siguiente implementa la funcionalidad de los controles de interfaz de usuario de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="766d2-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="766d2-110">El <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, y <xref:System.Windows.Controls.MediaElement.Stop%2A> métodos se usan para reproducir, pausar y detener el elemento multimedia, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="766d2-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="766d2-111">Cambiar el <xref:System.Windows.Controls.MediaElement.Position%2A> propiedad de la <xref:System.Windows.Controls.MediaElement> permite omitir de los medios.</span><span class="sxs-lookup"><span data-stu-id="766d2-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="766d2-112">Por último, el <xref:System.Windows.Controls.MediaElement.Volume%2A> y <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> propiedades se utilizan para ajustar la velocidad de reproducción y el volumen de los medios.</span><span class="sxs-lookup"><span data-stu-id="766d2-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="766d2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="766d2-113">See also</span></span>
- [<span data-ttu-id="766d2-114">Controlar un control MediaElement mediante un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="766d2-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
