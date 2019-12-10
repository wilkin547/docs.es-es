---
title: 'Cómo: Rechazar las actualizaciones automáticas de cuadros de diálogo de archivos'
ms.date: 03/30/2017
helpviewer_keywords:
- OpenFileDialog [Windows Forms], opt out of automatic upgrade
- file dialog box [Windows Forms], opt out of automatic upgrade
- Windows Vista file dialog box [Windows Forms], opt out of automatic upgrade
- SaveFileDialog [Windows Forms], opt out of automatic upgrade
- AutoUpgradeEnabled property
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
ms.openlocfilehash: 154953680426f98a9506feb0b8f4de25c873b795
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959687"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Cómo: Rechazar las actualizaciones automáticas de cuadros de diálogo de archivos
Cuando se usan las clases <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> en una aplicación, su apariencia y comportamiento dependen de la versión de Windows en la que se ejecuta la aplicación. Cuando una aplicación creada en el .NET Framework 2,0 o una versión anterior se muestra en Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> se muestran automáticamente con la apariencia y el comportamiento de Windows Vista. A partir del .NET Framework 3,0, puede rechazar la actualización automática para mostrar el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> con un comportamiento y apariencia de Windows XP.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Para rechazar las actualizaciones automáticas de cuadros de diálogo de archivos  
  
1. Establezca la propiedad <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> de <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> en `false` antes de mostrar el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FileDialog>
