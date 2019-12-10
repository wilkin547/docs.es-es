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
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="e1528-102">Cómo: Rechazar las actualizaciones automáticas de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="e1528-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="e1528-103">Cuando se usan las clases <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> en una aplicación, su apariencia y comportamiento dependen de la versión de Windows en la que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1528-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="e1528-104">Cuando una aplicación creada en el .NET Framework 2,0 o una versión anterior se muestra en Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> se muestran automáticamente con la apariencia y el comportamiento de Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e1528-104">When an application that was created on the .NET Framework 2.0 or earlier is displayed on Windows Vista, <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the Windows Vista appearance and behavior.</span></span> <span data-ttu-id="e1528-105">A partir del .NET Framework 3,0, puede rechazar la actualización automática para mostrar el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> con un comportamiento y apariencia de Windows XP.</span><span class="sxs-lookup"><span data-stu-id="e1528-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a Windows XP-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="e1528-106">Para rechazar las actualizaciones automáticas de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="e1528-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="e1528-107">Establezca la propiedad <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> de <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> en `false` antes de mostrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e1528-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1528-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1528-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
