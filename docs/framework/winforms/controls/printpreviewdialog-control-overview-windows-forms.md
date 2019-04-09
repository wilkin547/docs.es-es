---
title: Información general sobre el control PrintPreviewDialog (formularios Windows Forms)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32fbdd222e34f642d29255e6c594076b6d2a91e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188843"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.PrintPreviewDialog> control es un cuadro de diálogo preconfigurado que utiliza para mostrar cómo un [PrintDocument](printdocument-component-windows-forms.md) aparecerá cuando se imprima. Usar dentro de la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo. El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.  
  
## <a name="key-properties-and-methods"></a>Los métodos y propiedades de clave  
 Propiedad de clave del control es <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento para la vista preliminar. El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto. Con el fin de mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.Form.ShowDialog%2A> método. Suavizado de contorno puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; Para ello, establezca el <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> propiedad `true`.  
  
 Algunas propiedades están disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> que el <xref:System.Windows.Forms.PrintPreviewDialog> contiene. (No es necesario agregar esta <xref:System.Windows.Forms.PrintPreviewControl> al formulario; automáticamente está contenido dentro de la <xref:System.Windows.Forms.PrintPreviewDialog> al agregar el cuadro de diálogo al formulario.) Ejemplos de propiedades disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> son el <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades, que determinan el número de páginas que se muestran horizontal y verticalmente en el control. Puede tener acceso a la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> propiedad como `PrintPreviewDialog1.PrintPreviewControl.Columns` en Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` en Visual C#, o `printPreviewDialog1->PrintPreviewControl->Columns` en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="printpreviewdialog-performance"></a>Rendimiento de PrintPreviewDialog

En las siguientes condiciones, el <xref:System.Windows.Forms.PrintPreviewDialog> control inicializa muy lenta:

- Se utiliza una impresora de red.
- Las preferencias del usuario para esta impresora, como la configuración de dúplex, se modifican.
  
Para las aplicaciones que se ejecutan en .NET Framework 4.5.2, puede agregar la siguiente clave en el \<appSettings > sección del archivo de configuración para mejorar el rendimiento de <xref:System.Windows.Forms.PrintPreviewDialog> controlan la inicialización:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
Si el `EnablePrintPreviewOptimization` clave se establece en cualquier otro valor, o si la clave no está presente, no se aplica la optimización.

Para aplicaciones que se ejecutan en .NET Framework 4.6 o versiones posteriores, puede agregar el modificador siguiente a la [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ \<en tiempo de ejecución >](../../configure-apps/file-schema/runtime/index.md) sección del archivo de configuración de aplicación:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
Si el modificador no está presente o si se establece en cualquier otro valor, no se aplica la optimización. 

Si usas el <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> eventos para modificar la configuración de impresora, el rendimiento de la <xref:System.Windows.Forms.PrintPreviewDialog> control no mejorará incluso si se establece un modificador de configuración de optimización.  

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Información general sobre el control PrintPreviewControl](printpreviewcontrol-control-overview-windows-forms.md)
- [Control PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](dialog-box-controls-and-components-windows-forms.md)
