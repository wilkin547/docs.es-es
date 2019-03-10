---
title: Filtrar Reproducir un sonido incrustado en un recurso desde un formulario de Windows
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
ms.openlocfilehash: f52cac4ca16adee232fae6fe2c1540bf5d3cb8cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708189"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Filtrar Reproducir un sonido incrustado en un recurso desde un formulario de Windows
Puede usar el <xref:System.Media.SoundPlayer> clase para reproducir un sonido desde un recurso incrustado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
 Importar el <xref:System.Media?displayProperty=nameWithType> espacio de nombres.  
  
 Incluir el archivo de sonido como recurso incrustado en el proyecto.  
  
 Reemplazar "\<AssemblyName >" con el nombre del ensamblado en el que se incrusta el archivo de sonido. No incluya el sufijo ".dll".  
  
## <a name="see-also"></a>Vea también
- <xref:System.Media.SoundPlayer>
- [Cómo: Reproducir un sonido desde Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
- [Cómo: Repetir un sonido reproducido en un formulario de Windows](how-to-loop-a-sound-playing-on-a-windows-form.md)
