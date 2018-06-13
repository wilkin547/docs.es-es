---
title: 'Cómo: Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 4e4623c1c0fe7d082e4d1a1f404ddaa94e79fc2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533635"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Cómo: Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño
Puede establecer un <xref:System.Windows.Forms.ToolTip> cadena en el código o en el Diseñador de Windows Forms. Para obtener más información sobre la <xref:System.Windows.Forms.ToolTip> componente, vea [información general del componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-a-tooltip-programmatically"></a>Para establecer una información sobre herramientas mediante programación  
  
1.  Agregue el control que se mostrará la información sobre herramientas.  
  
2.  Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a>Para establecer una información sobre herramientas en el diseñador  
  
1.  Agregue un componente <xref:System.Windows.Forms.ToolTip> al formulario.  
  
2.  Seleccione el control que se muestre la información sobre herramientas, o se agregarán al formulario.  
  
3.  En el **propiedades** ventana, establezca el **información sobre herramientas en ToolTip1** valor a una cadena de texto adecuada.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Cambiar el retardo del componente ToolTip de Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [ToolTip (componente)](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
