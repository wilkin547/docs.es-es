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
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewDialog (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control es un cuadro de diálogo preconfigurado que se utiliza para mostrar cómo un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) aparecerá cuando se imprima. Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo. El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.  
  
## <a name="key-properties-and-methods"></a>Métodos y propiedades claves  
 Ninguna propiedad clave del control <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento en una vista previa. El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto. Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.Form.ShowDialog%2A> método. El suavizado puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; para utilizarla, establezca la <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> propiedad `true`.  
  
 Algunas propiedades están disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> que la <xref:System.Windows.Forms.PrintPreviewDialog> contiene. (No es necesario agregar este <xref:System.Windows.Forms.PrintPreviewControl> al formulario; se incluye automáticamente dentro de la <xref:System.Windows.Forms.PrintPreviewDialog> cuando se agrega el cuadro de diálogo al formulario.) Ejemplos de propiedades disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> son la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades, que determinan el número de páginas que se muestran horizontal y verticalmente en el control. Puede tener acceso a la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> propiedad como `PrintPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], o `printPreviewDialog1->PrintPreviewControl->Columns` en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="printpreviewdialog-performance"></a>Rendimiento de PrintPreviewDialog

En las siguientes condiciones, la <xref:System.Windows.Forms.PrintPreviewDialog> control inicializa muy lenta:

- Se usa una impresora de red.
- Las preferencias del usuario para esta impresora, como la configuración de dúplex, se han modificado.
  
Para aplicaciones que se ejecutan en .NET Framework 4.5.2, puede agregar la siguiente clave a la \<appSettings > sección de su archivo de configuración para mejorar el rendimiento de <xref:System.Windows.Forms.PrintPreviewDialog> controlan la inicialización:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
Si el `EnablePrintPreviewOptimization` clave se establece en cualquier otro valor, o si la clave no está presente, no se aplica la optimización.

Para aplicaciones que se ejecutan en .NET Framework 4.6 o versiones posteriores, puede agregar el siguiente modificador a la [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento en el [ \<en tiempo de ejecución >](../../configure-apps/file-schema/runtime/index.md) sección de su archivo de configuración de aplicación:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
Si el conmutador no está presente o si se establece en cualquier otro valor, no se aplicó la optimización. 

Si usas el <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> evento para modificar la configuración de impresora, el rendimiento de la <xref:System.Windows.Forms.PrintPreviewDialog> control no mejorará incluso si se ha establecido un modificador de configuración de optimización.  

## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Información general sobre el control PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog (control)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
