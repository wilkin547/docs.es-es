---
title: Filtrar Crear un cuadro de texto de sólo lectura (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: be85eedf272e596ceb10e7510b8c99ce6aed0727
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130733"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Filtrar Crear un cuadro de texto de sólo lectura (formularios Windows Forms)
Puede transformar un cuadro de texto editable de Windows Forms en un control de solo lectura. Por ejemplo, el cuadro de texto puede mostrar un valor que se puede editar normalmente pero actualmente, no puede ser debido al estado de la aplicación.  
  
### <a name="to-create-a-read-only-text-box"></a>Para crear un cuadro de texto de solo lectura  
  
1.  Establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad `true`. Con la propiedad establecida en `true`, los usuarios pueden desplazarse y resaltar texto en un cuadro de texto sin permitir que los cambios. Un **copia** comando es funcional en un cuadro de texto, pero **cortar** y **pegar** no son de comandos.  
  
    > [!NOTE]
    >  El <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución. Se puede modificar el contenido del cuadro de texto mediante programación en tiempo de ejecución mediante el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del cuadro de texto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Filtrar para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Filtrar para ver varias líneas en el control TextBox de formularios Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
