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
ms.openlocfilehash: e12134768d41589dedbeb5a00cab4244c7324f97
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722614"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="f2ee3-102">Cómo rechazar las actualizaciones automáticas de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="f2ee3-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="f2ee3-103">Cuando el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases se utilizan en una aplicación, su apariencia y comportamiento dependen de la versión de Windows se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2ee3-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="f2ee3-104">Cuando una aplicación que se creó en el [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] o versión anterior se muestra en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> se muestran automáticamente con el [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f2ee3-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="f2ee3-105">A partir de .NET Framework 3.0, puede rechazar la actualización automática para mostrar el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]: estilo de apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f2ee3-105">Starting in the .NET Framework 3.0, you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="f2ee3-106">Para rechazar las actualizaciones automáticas de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="f2ee3-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1. <span data-ttu-id="f2ee3-107">Establecer el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad de <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> a `false` antes de mostrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f2ee3-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ee3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2ee3-108">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
