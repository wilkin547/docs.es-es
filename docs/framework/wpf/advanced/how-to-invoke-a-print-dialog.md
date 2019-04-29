---
title: Procedimiento Invocar un cuadro de diálogo de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 2ced508eb83e2955fdcd1ad87fb6415e2052446f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757163"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="35248-102">Procedimiento Invocar un cuadro de diálogo de impresión</span><span class="sxs-lookup"><span data-stu-id="35248-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="35248-103">Para proporcionar la capacidad de imprimir desde la aplicación, simplemente puede crear y abrir un <xref:System.Windows.Controls.PrintDialog> objeto.</span><span class="sxs-lookup"><span data-stu-id="35248-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35248-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35248-104">Example</span></span>  
 <span data-ttu-id="35248-105">El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35248-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="35248-106">Es fácil de usar el control y se pueden crear instancias mediante el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado o código.</span><span class="sxs-lookup"><span data-stu-id="35248-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="35248-107">En el ejemplo siguiente se muestra cómo crear instancias y abrir el control de código y cómo imprimir a partir de él.</span><span class="sxs-lookup"><span data-stu-id="35248-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="35248-108">También muestra cómo asegurarse de que el cuadro de diálogo le ofrecerá la opción de establecer un intervalo de páginas específico.</span><span class="sxs-lookup"><span data-stu-id="35248-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="35248-109">El código de ejemplo se supone que hay un archivo FixedDocumentSequence.xps en la raíz de la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="35248-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="35248-110">Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar desde las impresoras instaladas en su equipo.</span><span class="sxs-lookup"><span data-stu-id="35248-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="35248-111">También tendrá la opción de seleccionar el [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) para crear un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivo en lugar de imprimir.</span><span class="sxs-lookup"><span data-stu-id="35248-111">They will also have the option of selecting the [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35248-112">El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que se describe en este tema, no debe confundirse con el <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35248-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="35248-113">En realidad, puede usar el <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> método sin siquiera abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="35248-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="35248-114">En ese sentido, el control puede usarse como un componente de impresión oculto.</span><span class="sxs-lookup"><span data-stu-id="35248-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="35248-115">Pero por motivos de rendimiento, sería mejor usar ya sea el <xref:System.Printing.PrintQueue.AddJob%2A> método o a uno de los muchos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="35248-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="35248-116">Para obtener más información acerca de esto, consulte [impresión de archivos XPS mediante programación](how-to-programmatically-print-xps-files.md) y.</span><span class="sxs-lookup"><span data-stu-id="35248-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35248-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="35248-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="35248-118">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="35248-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="35248-119">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="35248-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="35248-120">Escritor de documentos XPS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="35248-120">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
