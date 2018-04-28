---
title: 'Cómo: Invocar un cuadro de diálogo de impresión'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65ea65e13d3217466eeacdac4c386cc02c68b29a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="6d106-102">Cómo: Invocar un cuadro de diálogo de impresión</span><span class="sxs-lookup"><span data-stu-id="6d106-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="6d106-103">Para proporcionar la capacidad de imprimir desde la aplicación, simplemente puede crear y abrir un <xref:System.Windows.Controls.PrintDialog> objeto.</span><span class="sxs-lookup"><span data-stu-id="6d106-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d106-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d106-104">Example</span></span>  
 <span data-ttu-id="6d106-105">El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d106-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="6d106-106">El control es fácil de usar y se pueden crear instancias mediante el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o marcado del código.</span><span class="sxs-lookup"><span data-stu-id="6d106-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="6d106-107">En el ejemplo siguiente se muestra cómo crear una instancia y abrir el control en el código y cómo imprimir desde él.</span><span class="sxs-lookup"><span data-stu-id="6d106-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="6d106-108">También muestra cómo asegurarse de que el cuadro de diálogo le dará al usuario la opción de establecer un intervalo específico de páginas.</span><span class="sxs-lookup"><span data-stu-id="6d106-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="6d106-109">El código de ejemplo se supone que hay un archivo FixedDocumentSequence.xps en la raíz de la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="6d106-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="6d106-110">Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar entre las impresoras instaladas en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6d106-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="6d106-111">También tendrá la opción de seleccionar la [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) para crear un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivo en lugar de imprimir.</span><span class="sxs-lookup"><span data-stu-id="6d106-111">They will also have the option of selecting the [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d106-112">El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que se describe en este tema, no debe confundirse con el <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d106-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="6d106-113">En sentido estricto, puede usar el <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> método sin siquiera abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6d106-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="6d106-114">En ese sentido, el control puede usarse como componente de impresión oculto.</span><span class="sxs-lookup"><span data-stu-id="6d106-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="6d106-115">Pero por razones de rendimiento, sería mejor usar la <xref:System.Printing.PrintQueue.AddJob%2A> método o a uno de los muchos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="6d106-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="6d106-116">Para obtener más información al respecto, consulte [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) y.</span><span class="sxs-lookup"><span data-stu-id="6d106-116">For more about this, see [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d106-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d106-117">See Also</span></span>  
 <xref:System.Windows.Controls.PrintDialog>  
 [<span data-ttu-id="6d106-118">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="6d106-118">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="6d106-119">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="6d106-119">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="6d106-120">Escritor de documentos XPS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d106-120">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
