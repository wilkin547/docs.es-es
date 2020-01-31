---
title: Información general sobre el componente SaveFileDialog
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743102"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="22360-102">Información general sobre el componente SaveFileDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="22360-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="22360-103">El componente <xref:System.Windows.Forms.SaveFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="22360-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="22360-104">Es el mismo que el cuadro de diálogo **Guardar archivo** estándar utilizado por Windows.</span><span class="sxs-lookup"><span data-stu-id="22360-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="22360-105">Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="22360-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="22360-106">Trabajar con el componente SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="22360-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="22360-107">Úselo como una solución sencilla para permitir que los usuarios guarden archivos en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="22360-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="22360-108">Al confiar en los cuadros de diálogo estándar de Windows, la funcionalidad básica de las aplicaciones que crea es inmediatamente familiar para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="22360-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="22360-109">No obstante, tenga en cuenta que al usar el componente de <xref:System.Windows.Forms.SaveFileDialog>, debe escribir su propia lógica de guardado de archivos.</span><span class="sxs-lookup"><span data-stu-id="22360-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="22360-110">Puede usar el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="22360-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="22360-111">Puede abrir un archivo en modo de lectura y escritura mediante el método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="22360-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="22360-112">Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.SaveFileDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="22360-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="22360-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="22360-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="22360-114">SaveFileDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="22360-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
