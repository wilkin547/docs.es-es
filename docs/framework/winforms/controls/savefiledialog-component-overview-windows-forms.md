---
title: Información general sobre el componente SaveFileDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: be5f70e2e8b0d5143ef387819689ce95564a72d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537452"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="dd531-102">Información general sobre el componente SaveFileDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dd531-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="dd531-103">El componente <xref:System.Windows.Forms.SaveFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="dd531-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="dd531-104">Es el mismo que el estándar **Guardar archivo** cuadro de diálogo usado por Windows.</span><span class="sxs-lookup"><span data-stu-id="dd531-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="dd531-105">Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="dd531-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="dd531-106">Trabajar con el componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="dd531-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="dd531-107">Utilícelo como una solución sencilla para permitir que los usuarios guarden archivos en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="dd531-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="dd531-108">Al basarse en cuadros de diálogo estándar de Windows, la funcionalidad básica de las aplicaciones que cree es resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dd531-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="dd531-109">Tenga en cuenta, sin embargo, que, cuando uso el <xref:System.Windows.Forms.SaveFileDialog> componente, debe escribir su propia lógica de almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="dd531-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="dd531-110">Puede usar el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd531-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="dd531-111">Puede abrir un archivo en modo de lectura/escritura mediante el <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> método.</span><span class="sxs-lookup"><span data-stu-id="dd531-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="dd531-112">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.SaveFileDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="dd531-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd531-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd531-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="dd531-114">SaveFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="dd531-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
