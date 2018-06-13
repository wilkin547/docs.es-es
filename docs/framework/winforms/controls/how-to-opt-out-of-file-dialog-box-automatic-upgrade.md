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
ms.openlocfilehash: 380f8abe502c37e57207c43696158c1e3bdc7697
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532492"
---
# <a name="how-to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="3e4bc-102">Cómo: Rechazar las actualizaciones automáticas de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="3e4bc-102">How To: Opt Out of File Dialog Box Automatic Upgrade</span></span>
<span data-ttu-id="3e4bc-103">Cuando el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases se utilizan en una aplicación, su apariencia y comportamiento dependen de la versión de Windows que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e4bc-103">When the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes are used in an application, their appearance and behavior depend on the version of Windows the application is running on.</span></span> <span data-ttu-id="3e4bc-104">Cuando una aplicación que se creó en el [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] o versiones anteriores, se muestra en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> se muestran automáticamente con el [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3e4bc-104">When an application that was created on the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] or earlier is displayed on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> are automatically displayed with the [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] appearance and behavior.</span></span> <span data-ttu-id="3e4bc-105">A partir de la [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], puede rechazar la actualización automática para mostrar el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> con un [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-apariencia y el comportamiento de estilo.</span><span class="sxs-lookup"><span data-stu-id="3e4bc-105">Starting in the [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], you can opt out of the automatic upgrade to display the <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> with a [!INCLUDE[winxp](../../../../includes/winxp-md.md)]-style appearance and behavior.</span></span>  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a><span data-ttu-id="3e4bc-106">Para rechazar las actualizaciones automáticas de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="3e4bc-106">To opt out of file dialog box automatic upgrade</span></span>  
  
1.  <span data-ttu-id="3e4bc-107">Establecer el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad de <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> a `false` antes de mostrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e4bc-107">Set the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property of <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> to `false` before you display the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e4bc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e4bc-108">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>
