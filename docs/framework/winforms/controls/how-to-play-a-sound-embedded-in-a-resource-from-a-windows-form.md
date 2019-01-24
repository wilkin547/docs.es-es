---
title: Procedimiento Reproducir un sonido incrustado en un recurso desde un formulario de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 390f70acc99d8950a23ce514d90c79c3da765f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631339"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="e6d96-102">Procedimiento Reproducir un sonido incrustado en un recurso desde un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="e6d96-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="e6d96-103">Puede usar el <xref:System.Media.SoundPlayer> clase para reproducir un sonido desde un recurso incrustado.</span><span class="sxs-lookup"><span data-stu-id="e6d96-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6d96-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6d96-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e6d96-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e6d96-105">Compiling the Code</span></span>  
 <span data-ttu-id="e6d96-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e6d96-106">This example requires:</span></span>  
  
 <span data-ttu-id="e6d96-107">Importar el <xref:System.Media?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e6d96-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="e6d96-108">Incluir el archivo de sonido como recurso incrustado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e6d96-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="e6d96-109">Reemplazar "\<AssemblyName >" con el nombre del ensamblado en el que se incrusta el archivo de sonido.</span><span class="sxs-lookup"><span data-stu-id="e6d96-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="e6d96-110">No incluya el sufijo ".dll".</span><span class="sxs-lookup"><span data-stu-id="e6d96-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d96-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6d96-111">See also</span></span>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="e6d96-112">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e6d96-112">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="e6d96-113">Cómo: Repetir un sonido reproducido en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="e6d96-113">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
