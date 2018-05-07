---
title: 'Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms
Formularios Windows Forms <xref:System.Windows.Forms.Label> controles pueden utilizarse para definir teclas de acceso para otros controles. Al definir una tecla de acceso en un control de etiqueta, el usuario puede presionar la tecla ALT y el carácter designado para mover el foco al control que sigue en el orden de tabulación. Dado que las etiquetas no pueden recibir el foco, el foco automáticamente se desplaza al siguiente control en el orden de tabulación. Utilice esta técnica para asignar teclas de acceso a cuadros de texto, cuadros combinados, cuadros de lista y cuadrículas de datos.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Para asignar una tecla de acceso a un control con una etiqueta  
  
1.  Dibuje primero la etiqueta y, a continuación, dibuje el otro control.  
  
     -o bien-  
  
     Dibuje los controles en cualquier orden y establezca el <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad de la etiqueta hasta uno menos que el otro control.  
  
2.  Establezca la etiqueta <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true`.  
  
3.  Utilice una y comercial (&) en la etiqueta <xref:System.Windows.Forms.Label.Text%2A> propiedad para asignar la tecla de acceso para la etiqueta. Para obtener más información, consulte [crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Puede que desee mostrar una y comercial en un control de etiqueta, en lugar de usarlos para crear teclas de acceso. Esto puede ocurrir si enlaza un control de etiqueta a un campo en un conjunto de registros donde los datos incluyen símbolos de y comercial. Para mostrar una y comercial en un control label, establezca el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `false`. Si desea mostrar una y comercial y también tienen una clave de acceso, establecer el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true` e indique la tecla de acceso con una y comercial (&) y la y comercial para mostrar con dos signos de y comercial.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Etiqueta (control)](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
