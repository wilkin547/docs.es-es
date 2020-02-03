---
title: Información general sobre el componente FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745729"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="7c7e6-102">Información general del componente FolderBrowserDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7c7e6-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="7c7e6-103">El componente <xref:System.Windows.Forms.FolderBrowserDialog> de Windows Forms es un cuadro de diálogo modal que se usa para examinar y seleccionar carpetas.</span><span class="sxs-lookup"><span data-stu-id="7c7e6-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="7c7e6-104">También se pueden crear nuevas carpetas desde el <xref:System.Windows.Forms.FolderBrowserDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="7c7e6-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="7c7e6-105">Para seleccionar archivos, en lugar de carpetas, use el componente [OpenFileDialog](openfiledialog-component-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="7c7e6-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="7c7e6-106">El componente de <xref:System.Windows.Forms.FolderBrowserDialog> se muestra en tiempo de ejecución mediante el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c7e6-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="7c7e6-107">Establezca la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> para determinar la carpeta de nivel superior y todas las subcarpetas que aparecerán en la vista de árbol del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7c7e6-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="7c7e6-108">Una vez que se muestra el cuadro de diálogo, puede usar la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> para obtener la ruta de acceso de la carpeta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7c7e6-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="7c7e6-109">Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.FolderBrowserDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7c7e6-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c7e6-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c7e6-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="7c7e6-111">Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c7e6-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="7c7e6-112">FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="7c7e6-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
