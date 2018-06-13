---
title: 'Cómo: Reproducir un sonido incrustado en un recurso desde Windows Forms'
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
ms.openlocfilehash: c9dc8499e2d12ed17f9b409a805148d08da894fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532140"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Cómo: Reproducir un sonido incrustado en un recurso desde Windows Forms
Puede usar el <xref:System.Media.SoundPlayer> clase para reproducir un sonido desde un recurso incrustado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
 Importar el <xref:System.Media?displayProperty=nameWithType> espacio de nombres.  
  
 Incluir el archivo de sonido como recurso incrustado en el proyecto.  
  
 Reemplazar "\<AssemblyName >" con el nombre del ensamblado en el que se incrusta el archivo de sonido. No incluya el sufijo ".dll".  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer>  
 [Cómo: Reproducir un sonido desde Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [Cómo: Repetir la reproducción de un sonido en Windows Forms](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
