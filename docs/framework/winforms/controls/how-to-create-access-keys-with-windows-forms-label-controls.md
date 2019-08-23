---
title: Procedimiento para crear teclas de acceso con controles Label de formularios Windows Forms
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
ms.openlocfilehash: dd7f238f8c20ba990158f23344e36376d3b1cb7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950535"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Procedimiento para crear teclas de acceso con controles Label de formularios Windows Forms
Windows Forms <xref:System.Windows.Forms.Label> controles se pueden usar para definir teclas de acceso para otros controles. Al definir una tecla de acceso en un control etiqueta, el usuario puede presionar la tecla ALT más el carácter que designe para desplazar el foco al control que le sigue en el orden de tabulación. Dado que las etiquetas no pueden recibir el foco, el foco se mueve automáticamente al siguiente control en el orden de tabulación. Utilice esta técnica para asignar teclas de acceso a cuadros de texto, cuadros combinados, cuadros de lista y cuadrículas de datos.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Para asignar una tecla de acceso a un control con una etiqueta  
  
1. Dibuje primero la etiqueta y, a continuación, dibuje el otro control.  
  
     -o bien-  
  
     Dibuje los controles en cualquier orden y establezca la <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad de la etiqueta en uno menos que el otro control.  
  
2. Establezca la propiedad de <xref:System.Windows.Forms.Label.UseMnemonic%2A> la etiqueta `true`en.  
  
3. Use una y comercial (&) en la propiedad <xref:System.Windows.Forms.Label.Text%2A> de la etiqueta para asignar la tecla de acceso de la etiqueta. Para obtener más información, vea [crear claves de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    > Puede que desee mostrar los signos de y comercial en un control etiqueta, en lugar de usarlos para crear teclas de acceso. Esto puede ocurrir si se enlaza un control de etiqueta a un campo de un conjunto de registros en el que los datos incluyen y comercial. Para mostrar los signos de y comercial en un control <xref:System.Windows.Forms.Label.UseMnemonic%2A> etiqueta, `false`establezca la propiedad en. Si desea mostrar y también una tecla de acceso, establezca la <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad en `true` e indique la tecla de acceso con una y comercial (&) y la y comercial para que se muestren con dos signos de y comercial.  
  
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

- [Cómo: Cambiar el tamaño de un control etiqueta de Windows Forms para ajustar su contenido](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Información general sobre el control Label](label-control-overview-windows-forms.md)
- [Etiqueta (control)](label-control-windows-forms.md)
