---
title: "Cómo: Reproducir un sonido incrustado en un recurso desde Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82e143a6c405d4f3065c18a1a118891e0e692b93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="dc973-102">Cómo: Reproducir un sonido incrustado en un recurso desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc973-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="dc973-103">Puede usar el <xref:System.Media.SoundPlayer> clase para reproducir un sonido desde un recurso incrustado.</span><span class="sxs-lookup"><span data-stu-id="dc973-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc973-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc973-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc973-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="dc973-105">Compiling the Code</span></span>  
 <span data-ttu-id="dc973-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="dc973-106">This example requires:</span></span>  
  
 <span data-ttu-id="dc973-107">Importar el <xref:System.Media?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dc973-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="dc973-108">Incluir el archivo de sonido como recurso incrustado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="dc973-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="dc973-109">Reemplazar "\<AssemblyName >" con el nombre del ensamblado en el que se incrusta el archivo de sonido.</span><span class="sxs-lookup"><span data-stu-id="dc973-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="dc973-110">No incluya el sufijo ".dll".</span><span class="sxs-lookup"><span data-stu-id="dc973-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc973-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc973-111">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 [<span data-ttu-id="dc973-112">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc973-112">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="dc973-113">Cómo: Repetir la reproducción de un sonido en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc973-113">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
