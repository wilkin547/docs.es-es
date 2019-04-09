---
title: Cómo rechazar las actualizaciones automáticas de cuadros de diálogo de archivos
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 6fd34e1127747739423f6402f128194a3a39f5e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089154"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Cómo rechazar las actualizaciones automáticas de cuadros de diálogo de archivos
Cuando el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases se utilizan en una aplicación, su apariencia y comportamiento dependen de la versión de Windows se ejecuta la aplicación. Cuando una aplicación que se creó en el [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] o versión anterior se muestra en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> se muestran automáticamente con el [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] apariencia y comportamiento. A partir de la [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], puede rechazar la actualización automática para mostrar el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-apariencia y el comportamiento de estilo.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Para rechazar las actualizaciones automáticas de cuadros de diálogo de archivos  
  
1.  Establecer el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad de <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> a `false` antes de mostrar el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FileDialog>
