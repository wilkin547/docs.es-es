---
title: 'Cómo: Invocar un cuadro de diálogo de impresión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: f7ef3312d876324b44b055d70fd22e3fba075ec6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095182"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="0d59a-102">Cómo: Invocar un cuadro de diálogo de impresión</span><span class="sxs-lookup"><span data-stu-id="0d59a-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="0d59a-103">Para proporcionar la capacidad de imprimir desde la aplicación, puede simplemente crear y abrir un objeto de <xref:System.Windows.Controls.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="0d59a-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d59a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d59a-104">Example</span></span>  
 <span data-ttu-id="0d59a-105">El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para el envío de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y trabajo XPS.</span><span class="sxs-lookup"><span data-stu-id="0d59a-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and XPS job submission.</span></span> <span data-ttu-id="0d59a-106">El control es fácil de usar y se puede crear una instancia de él mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado o código.</span><span class="sxs-lookup"><span data-stu-id="0d59a-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="0d59a-107">En el ejemplo siguiente se muestra cómo crear una instancia de y abrir el control en el código y cómo imprimir desde él.</span><span class="sxs-lookup"><span data-stu-id="0d59a-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="0d59a-108">También se muestra cómo asegurarse de que el cuadro de diálogo proporciona al usuario la opción de configurar un intervalo específico de páginas.</span><span class="sxs-lookup"><span data-stu-id="0d59a-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="0d59a-109">En el código de ejemplo se supone que hay un archivo FixedDocumentSequence. XPS en la raíz de la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="0d59a-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="0d59a-110">Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar entre las impresoras instaladas en su equipo.</span><span class="sxs-lookup"><span data-stu-id="0d59a-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="0d59a-111">También tendrán la opción de seleccionar el escritor de [documentos XPS de Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer) para crear un archivo XML Paper Specification (XPS) en lugar de imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="0d59a-111">They will also have the option of selecting the [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer) to create an XML Paper Specification (XPS) file instead of printing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d59a-112">El control <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> de WPF, que se describe en este tema, no se debe confundir con el componente <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0d59a-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of WPF, which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="0d59a-113">En realidad, puede usar el método <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> sin abrir nunca el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0d59a-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="0d59a-114">En ese sentido, el control se puede usar como un componente de impresión no visible.</span><span class="sxs-lookup"><span data-stu-id="0d59a-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="0d59a-115">Sin embargo, por motivos de rendimiento, sería mejor utilizar el método <xref:System.Printing.PrintQueue.AddJob%2A> o uno de los muchos métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="0d59a-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="0d59a-116">Para obtener más información, consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md) y.</span><span class="sxs-lookup"><span data-stu-id="0d59a-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d59a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d59a-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="0d59a-118">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="0d59a-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="0d59a-119">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="0d59a-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="0d59a-120">Escritor de documentos XPS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d59a-120">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
