---
title: Filtrar Crear teclas de acceso con controles Label de formularios de Windows
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
ms.openlocfilehash: 227880ad15e452df3f05807c41f3923cccb6fe3a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708306"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Filtrar Crear teclas de acceso con controles Label de formularios de Windows
Windows Forms <xref:System.Windows.Forms.Label> controles pueden usarse para definir teclas de acceso para otros controles. Al definir una clave de acceso en un control de etiqueta, el usuario puede presionar la tecla ALT y el carácter designado para mover el foco al control que le sigue en el orden de tabulación. Dado que las etiquetas no pueden recibir el foco, el foco se mueve automáticamente al siguiente control en el orden de tabulación. Use esta técnica para asignar las claves de acceso a los cuadros de texto, cuadros combinados, cuadros de lista y cuadrículas de datos.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Para asignar una tecla de acceso a un control con una etiqueta  
  
1.  Dibuje primero la etiqueta y, a continuación, dibuje el control de otro.  
  
     O bien  
  
     Dibuje los controles en cualquier orden y establezca el <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad de la etiqueta a menos que el otro control.  
  
2.  Establezca la etiqueta <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true`.  
  
3.  Utilice una y comercial (&) en la etiqueta <xref:System.Windows.Forms.Label.Text%2A> propiedad para asignar la clave de acceso para la etiqueta. Para obtener más información, consulte [crear teclas de acceso para controles de formularios Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Es posible que desee mostrar una y comercial en un control de etiqueta, en lugar de usar para crear claves de acceso. Esto puede ocurrir si enlaza un control de etiqueta a un campo en un conjunto de registros donde los datos incluyen los y comerciales. Para mostrar una y comercial en un control label, establezca el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `false`. Si desea mostrar una y comercial y tener también una clave de acceso, establezca el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true` e indique la clave de acceso con una y comercial (&) y la y comercial para mostrar con dos signos de y comercial.  
  
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
- [Cómo: Tamaño de un Control de etiqueta de Windows Forms para ajustar su contenido](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Información general sobre el control Label](label-control-overview-windows-forms.md)
- [Etiqueta (control)](label-control-windows-forms.md)
