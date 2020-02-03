---
title: Información general sobre el control PrintPreviewDialog
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741412"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="9c9cb-102">Información general sobre el control PrintPreviewDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9c9cb-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="9c9cb-103">El control de <xref:System.Windows.Forms.PrintPreviewDialog> de Windows Forms es un cuadro de diálogo preconfigurado que se usa para mostrar cómo aparecerá [PrintDocument](printdocument-component-windows-forms.md) cuando se imprima.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="9c9cb-104">Úselo en su aplicación basada en Windows como una solución sencilla en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="9c9cb-105">El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="9c9cb-106">Propiedades y métodos clave</span><span class="sxs-lookup"><span data-stu-id="9c9cb-106">Key properties and methods</span></span>

<span data-ttu-id="9c9cb-107">La propiedad de clave del control es <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento cuya vista previa se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="9c9cb-108">El documento debe ser un objeto de <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="9c9cb-109">Para mostrar el cuadro de diálogo, debe llamar a su método <xref:System.Windows.Forms.Form.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="9c9cb-110">El suavizado de contorno puede hacer que el texto parezca más suave, pero también puede hacer que la pantalla sea más lenta. para usarlo, establezca la propiedad <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="9c9cb-111">Algunas propiedades están disponibles a través del <xref:System.Windows.Forms.PrintPreviewControl> que contiene el <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="9c9cb-112">(No tiene que agregar este <xref:System.Windows.Forms.PrintPreviewControl> al formulario; se incluye automáticamente en el <xref:System.Windows.Forms.PrintPreviewDialog> al agregar el cuadro de diálogo al formulario). Algunos ejemplos de propiedades disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> son las propiedades <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, que determinan el número de páginas que se muestran horizontal y verticalmente en el control.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="9c9cb-113">Puede tener acceso a la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> como `PrintPreviewDialog1.PrintPreviewControl.Columns` en Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` en C#visual o `printPreviewDialog1->PrintPreviewControl->Columns` en Visual C++.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="9c9cb-114">Rendimiento de PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="9c9cb-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="9c9cb-115">En las siguientes condiciones, el control de <xref:System.Windows.Forms.PrintPreviewDialog> se inicializa muy lentamente:</span><span class="sxs-lookup"><span data-stu-id="9c9cb-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="9c9cb-116">Se utiliza una impresora de red.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-116">A network printer is used.</span></span>
- <span data-ttu-id="9c9cb-117">Se modifican las preferencias de usuario para esta impresora, como la configuración dúplex.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="9c9cb-118">En el caso de las aplicaciones que se ejecutan en el .NET Framework 4.5.2, puede Agregar la siguiente clave a la sección \<appSettings > del archivo de configuración para mejorar el rendimiento de la inicialización del control de <xref:System.Windows.Forms.PrintPreviewDialog>:</span><span class="sxs-lookup"><span data-stu-id="9c9cb-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="9c9cb-119">Si la clave de `EnablePrintPreviewOptimization` se establece en cualquier otro valor, o si la clave no está presente, no se aplica la optimización.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="9c9cb-120">En el caso de las aplicaciones que se ejecutan en el .NET Framework 4,6 o versiones posteriores, puede Agregar el siguiente modificador al elemento [\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [> en tiempo de ejecución de\<](../../configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9c9cb-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="9c9cb-121">Si el modificador no está presente o se establece en cualquier otro valor, no se aplica la optimización.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="9c9cb-122">Si usa el evento <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> para modificar la configuración de la impresora, el rendimiento del control <xref:System.Windows.Forms.PrintPreviewDialog> no mejorará incluso si se ha establecido un modificador de configuración de optimización.</span><span class="sxs-lookup"><span data-stu-id="9c9cb-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c9cb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c9cb-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="9c9cb-124">Información general sobre el control PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="9c9cb-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="9c9cb-125">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="9c9cb-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="9c9cb-126">Controles y componentes de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="9c9cb-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
