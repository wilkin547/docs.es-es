---
title: Información general sobre el componente OpenFileDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: 24327ded50ac927642e2687b40b1f10de9bdf41e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211719"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="b5bb4-102">Información general sobre el componente OpenFileDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b5bb4-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="b5bb4-103">El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="b5bb4-104">Es el mismo **abrir archivo** cuadro de diálogo expuesto por el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="b5bb4-105">Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="b5bb4-106">Utilice este componente</span><span class="sxs-lookup"><span data-stu-id="b5bb4-106">Use this component</span></span>

<span data-ttu-id="b5bb4-107">Utilice este componente dentro de la aplicación basada en Windows como una solución sencilla para la selección de archivo en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="b5bb4-108">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="b5bb4-109">Tenga en cuenta, sin embargo, que, cuando uso el <xref:System.Windows.Forms.OpenFileDialog> componente, debe escribir su propia lógica de apertura de archivos.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="b5bb4-110">Use el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="b5bb4-111">Puede permitir a los usuarios seleccionados varios archivos que desea abrir con el <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="b5bb4-112">Además, puede usar el <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> propiedad para determinar si aparece una casilla de solo lectura en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="b5bb4-113">El <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> propiedad indica si está seleccionada la casilla de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="b5bb4-114">Por último, el <xref:System.Windows.Forms.FileDialog.Filter%2A> propiedad establece la cadena de filtro de nombre de archivo actual, que determina las opciones que aparecen en el cuadro "Archivos de tipo" en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="b5bb4-115">Cuando se agrega a un formulario, el <xref:System.Windows.Forms.OpenFileDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b5bb4-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5bb4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5bb4-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="b5bb4-117">OpenFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="b5bb4-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
