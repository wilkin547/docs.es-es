---
title: "Información general sobre el control PrintPreviewDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 01/08/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1228a3cf39ea412cde341c4c4b8b83e0ab2f0299
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="5cf8b-102">Información general sobre el control PrintPreviewDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5cf8b-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="5cf8b-103">Los formularios Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control es un cuadro de diálogo preconfigurado que se utiliza para mostrar cómo un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) aparecerá cuando se imprima.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="5cf8b-104">Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="5cf8b-105">El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="5cf8b-106">Métodos y propiedades claves</span><span class="sxs-lookup"><span data-stu-id="5cf8b-106">Key properties and methods</span></span>  
 <span data-ttu-id="5cf8b-107">Ninguna propiedad clave del control <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento en una vista previa.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="5cf8b-108">El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="5cf8b-109">Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.Form.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="5cf8b-110">El suavizado puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; para utilizarla, establezca la <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="5cf8b-111">Algunas propiedades están disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> que la <xref:System.Windows.Forms.PrintPreviewDialog> contiene.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="5cf8b-112">(No es necesario agregar este <xref:System.Windows.Forms.PrintPreviewControl> al formulario; se incluye automáticamente dentro de la <xref:System.Windows.Forms.PrintPreviewDialog> cuando se agrega el cuadro de diálogo al formulario.) Ejemplos de propiedades disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> son la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades, que determinan el número de páginas que se muestran horizontal y verticalmente en el control.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="5cf8b-113">Puede tener acceso a la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> propiedad como `PrintPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], o `printPreviewDialog1->PrintPreviewControl->Columns` en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cf8b-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="5cf8b-114">Rendimiento de PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="5cf8b-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="5cf8b-115">En las siguientes condiciones, la <xref:System.Windows.Forms.PrintPreviewDialog> control inicializa muy lenta:</span><span class="sxs-lookup"><span data-stu-id="5cf8b-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="5cf8b-116">Se usa una impresora de red.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-116">A network printer is used.</span></span>
- <span data-ttu-id="5cf8b-117">Las preferencias del usuario para esta impresora, como la configuración de dúplex, se han modificado.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="5cf8b-118">Para aplicaciones que se ejecutan en .NET Framework 4.5.2, puede agregar la siguiente clave a la \<appSettings > sección de su archivo de configuración para mejorar el rendimiento de <xref:System.Windows.Forms.PrintPreviewDialog> controlan la inicialización:</span><span class="sxs-lookup"><span data-stu-id="5cf8b-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="5cf8b-119">Si el `EnablePrintPreviewOptimization` clave se establece en cualquier otro valor, o si la clave no está presente, no se aplica la optimización.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="5cf8b-120">Para aplicaciones que se ejecutan en .NET Framework 4.6 o versiones posteriores, puede agregar el siguiente modificador a la [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ \<en tiempo de ejecución >](../../configure-apps/file-schema/runtime/index.md) sección de su archivo de configuración de aplicación:</span><span class="sxs-lookup"><span data-stu-id="5cf8b-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="5cf8b-121">Si el conmutador no está presente o si se establece en cualquier otro valor, no se aplicó la optimización.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="5cf8b-122">Si usas el <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> evento para modificar la configuración de impresora, el rendimiento de la <xref:System.Windows.Forms.PrintPreviewDialog> control no mejorará incluso si se ha establecido un modificador de configuración de optimización.</span><span class="sxs-lookup"><span data-stu-id="5cf8b-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5cf8b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cf8b-123">See also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="5cf8b-124">Información general sobre el control PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="5cf8b-124">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="5cf8b-125">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="5cf8b-125">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="5cf8b-126">Controles y componentes de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="5cf8b-126">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
