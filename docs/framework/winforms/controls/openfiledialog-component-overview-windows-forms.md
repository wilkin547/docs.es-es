---
title: "Información general sobre el componente OpenFileDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3e5dc6630d9bc7a2090a28daabbf08eeed59005
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="6288c-102">Información general sobre el componente OpenFileDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6288c-102">OpenFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="6288c-103">El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="6288c-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="6288c-104">Es el mismo **archivos abiertos** cuadro de diálogo expuesto por el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="6288c-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="6288c-105">Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="6288c-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="using-this-component"></a><span data-ttu-id="6288c-106">Utilizando este componente</span><span class="sxs-lookup"><span data-stu-id="6288c-106">Using this Component</span></span>  
 <span data-ttu-id="6288c-107">Utilice este componente dentro de la aplicación basada en Windows como una solución sencilla para seleccionar archivos, en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6288c-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="6288c-108">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6288c-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="6288c-109">Tenga en cuenta, sin embargo, que, cuando uso el <xref:System.Windows.Forms.OpenFileDialog> componente, debe escribir su propia lógica de apertura de archivos.</span><span class="sxs-lookup"><span data-stu-id="6288c-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>  
  
 <span data-ttu-id="6288c-110">Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6288c-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="6288c-111">Puede permitir a los usuarios seleccionar varios archivos que desea abrir con el <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6288c-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="6288c-112">Además, puede usar el <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> propiedad para determinar si en el cuadro de diálogo aparece una casilla de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6288c-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="6288c-113">El <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> propiedad indica si está seleccionada la casilla de verificación sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="6288c-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="6288c-114">Por último, el <xref:System.Windows.Forms.FileDialog.Filter%2A> propiedad establece la cadena de filtro de nombre de archivo actual, que determina las opciones que aparecen en el cuadro "Archivos de tipo" en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6288c-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>  
  
 <span data-ttu-id="6288c-115">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.OpenFileDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6288c-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6288c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6288c-116">See Also</span></span>  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [<span data-ttu-id="6288c-117">OpenFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="6288c-117">OpenFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
