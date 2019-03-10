---
title: Información general del componente FolderBrowserDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: d08eb456ea2d2d3b805d3df7e0e79b26ea7d415e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708254"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="80b5d-102">Información general del componente FolderBrowserDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="80b5d-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="80b5d-103">Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente es un cuadro de diálogo modal que se utiliza para examinar y seleccionar carpetas.</span><span class="sxs-lookup"><span data-stu-id="80b5d-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="80b5d-104">También se pueden crear nuevas carpetas desde el <xref:System.Windows.Forms.FolderBrowserDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="80b5d-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80b5d-105">Para seleccionar archivos, en lugar de carpetas, use el [OpenFileDialog](openfiledialog-component-windows-forms.md) componente.</span><span class="sxs-lookup"><span data-stu-id="80b5d-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="80b5d-106">El <xref:System.Windows.Forms.FolderBrowserDialog> componente se muestra en tiempo de ejecución mediante el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="80b5d-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="80b5d-107">Establecer el <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad para determinar la carpeta de nivel superior y las subcarpetas que aparecerán en la vista de árbol del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="80b5d-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="80b5d-108">Una vez mostrado el cuadro de diálogo, se puede utilizar el <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad va a obtener la ruta de acceso de la carpeta que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="80b5d-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="80b5d-109">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.FolderBrowserDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="80b5d-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b5d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="80b5d-110">See also</span></span>
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="80b5d-111">Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="80b5d-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="80b5d-112">FolderBrowserDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="80b5d-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
