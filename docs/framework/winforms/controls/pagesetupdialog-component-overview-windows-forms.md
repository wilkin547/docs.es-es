---
title: Información general sobre el componente PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744332"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="f45e5-102">Información general sobre el componente PageSetupDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f45e5-102">PageSetupDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="f45e5-103">El componente <xref:System.Windows.Forms.PageSetupDialog> de Windows Forms es un cuadro de diálogo preconfigurado que se usa para establecer los detalles de la página para imprimir en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="f45e5-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="f45e5-104">Úselo en su aplicación basada en Windows como una solución sencilla para que los usuarios establezcan preferencias de página en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f45e5-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="f45e5-105">Puede permitir que los usuarios establezcan ajustes de borde y margen, encabezados y pies de página, así como orientación vertical u horizontal.</span><span class="sxs-lookup"><span data-stu-id="f45e5-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="f45e5-106">Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f45e5-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="f45e5-107">Propiedades y métodos clave</span><span class="sxs-lookup"><span data-stu-id="f45e5-107">Key Properties and Methods</span></span>

<span data-ttu-id="f45e5-108">Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f45e5-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="f45e5-109">Este componente tiene propiedades que se pueden establecer relacionadas con una sola página (clase<xref:System.Drawing.Printing.PrintDocument>) o con cualquier documento (clase<xref:System.Drawing.Printing.PageSettings>).</span><span class="sxs-lookup"><span data-stu-id="f45e5-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="f45e5-110">Además, el componente de <xref:System.Windows.Forms.PageSetupDialog> se puede utilizar para determinar la configuración específica de la impresora, que se almacena en la clase <xref:System.Drawing.Printing.PrinterSettings>.</span><span class="sxs-lookup"><span data-stu-id="f45e5-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>

<span data-ttu-id="f45e5-111">Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.PageSetupDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f45e5-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="f45e5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f45e5-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="f45e5-113">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="f45e5-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
