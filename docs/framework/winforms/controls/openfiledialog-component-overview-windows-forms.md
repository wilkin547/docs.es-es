---
title: Información general sobre el componente OpenFileDialog
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728438"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="5f1d7-102">Información general sobre el componente OpenFileDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5f1d7-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="5f1d7-103">El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="5f1d7-104">Es el mismo cuadro de diálogo **Abrir archivo** expuesto por el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="5f1d7-105">Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="5f1d7-106">Usar este componente</span><span class="sxs-lookup"><span data-stu-id="5f1d7-106">Use this component</span></span>

<span data-ttu-id="5f1d7-107">Use este componente en su aplicación basada en Windows como una solución sencilla para la selección de archivos en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="5f1d7-108">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="5f1d7-109">No obstante, tenga en cuenta que al usar el componente de <xref:System.Windows.Forms.OpenFileDialog>, debe escribir su propia lógica de apertura de archivos.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="5f1d7-110">Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="5f1d7-111">Puede permitir que los usuarios seleccionen varios archivos para que se abran con la propiedad <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="5f1d7-112">Además, puede utilizar la propiedad <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> para determinar si aparece una casilla de solo lectura en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="5f1d7-113">La propiedad <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> indica si la casilla de solo lectura está activada.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="5f1d7-114">Por último, la propiedad <xref:System.Windows.Forms.FileDialog.Filter%2A> establece la cadena actual de filtro de nombres de archivo, que determina las opciones que aparecen en el cuadro "archivos de tipo" del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="5f1d7-115">Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.OpenFileDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f1d7-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f1d7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f1d7-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="5f1d7-117">OpenFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="5f1d7-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
