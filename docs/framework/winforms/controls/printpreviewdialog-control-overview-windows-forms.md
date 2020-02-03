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
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewDialog (Windows Forms)

El control de <xref:System.Windows.Forms.PrintPreviewDialog> de Windows Forms es un cuadro de diálogo preconfigurado que se usa para mostrar cómo aparecerá [PrintDocument](printdocument-component-windows-forms.md) cuando se imprima. Úselo en su aplicación basada en Windows como una solución sencilla en lugar de configurar su propio cuadro de diálogo. El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.

## <a name="key-properties-and-methods"></a>Propiedades y métodos clave

La propiedad de clave del control es <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento cuya vista previa se va a obtener. El documento debe ser un objeto de <xref:System.Drawing.Printing.PrintDocument>. Para mostrar el cuadro de diálogo, debe llamar a su método <xref:System.Windows.Forms.Form.ShowDialog%2A>. El suavizado de contorno puede hacer que el texto parezca más suave, pero también puede hacer que la pantalla sea más lenta. para usarlo, establezca la propiedad <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> en `true`.

Algunas propiedades están disponibles a través del <xref:System.Windows.Forms.PrintPreviewControl> que contiene el <xref:System.Windows.Forms.PrintPreviewDialog>. (No tiene que agregar este <xref:System.Windows.Forms.PrintPreviewControl> al formulario; se incluye automáticamente en el <xref:System.Windows.Forms.PrintPreviewDialog> al agregar el cuadro de diálogo al formulario). Algunos ejemplos de propiedades disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> son las propiedades <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, que determinan el número de páginas que se muestran horizontal y verticalmente en el control. Puede tener acceso a la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> como `PrintPreviewDialog1.PrintPreviewControl.Columns` en Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` en C#visual o `printPreviewDialog1->PrintPreviewControl->Columns` en Visual C++.

## <a name="printpreviewdialog-performance"></a>Rendimiento de PrintPreviewDialog

En las siguientes condiciones, el control de <xref:System.Windows.Forms.PrintPreviewDialog> se inicializa muy lentamente:

- Se utiliza una impresora de red.
- Se modifican las preferencias de usuario para esta impresora, como la configuración dúplex.

En el caso de las aplicaciones que se ejecutan en el .NET Framework 4.5.2, puede Agregar la siguiente clave a la sección \<appSettings > del archivo de configuración para mejorar el rendimiento de la inicialización del control de <xref:System.Windows.Forms.PrintPreviewDialog>:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

Si la clave de `EnablePrintPreviewOptimization` se establece en cualquier otro valor, o si la clave no está presente, no se aplica la optimización.

En el caso de las aplicaciones que se ejecutan en el .NET Framework 4,6 o versiones posteriores, puede Agregar el siguiente modificador al elemento [\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [> en tiempo de ejecución de\<](../../configure-apps/file-schema/runtime/index.md) del archivo de configuración de la aplicación:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

Si el modificador no está presente o se establece en cualquier otro valor, no se aplica la optimización.

Si usa el evento <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> para modificar la configuración de la impresora, el rendimiento del control <xref:System.Windows.Forms.PrintPreviewDialog> no mejorará incluso si se ha establecido un modificador de configuración de optimización.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Información general sobre el control PrintPreviewControl](printpreviewcontrol-control-overview-windows-forms.md)
- [PrintPreviewDialog (control)](printpreviewdialog-control-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](dialog-box-controls-and-components-windows-forms.md)
