---
title: Filtrar para establecer información sobre herramientas en controles de formularios Windows Forms en tiempo de diseño
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: cc8f8c620516a943d6d70187e19b72f5a2a99888
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301339"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Filtrar para establecer información sobre herramientas en controles de formularios Windows Forms en tiempo de diseño
Puede establecer un <xref:System.Windows.Forms.ToolTip> cadena en el código o en el Diseñador de Windows Forms. Para obtener más información sobre la <xref:System.Windows.Forms.ToolTip> componente, vea [información general del componente ToolTip](tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-a-tooltip-programmatically"></a>Para establecer una información sobre herramientas mediante programación  
  
1. Agregue el control que se mostrará la información sobre herramientas.  
  
2. Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.  
  
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
  
1. Agregue un componente <xref:System.Windows.Forms.ToolTip> al formulario.  
  
2. Seleccione el control que se mostrará la información sobre herramientas, o agréguelo al formulario.  
  
3. En el **propiedades** ventana, establezca el **información sobre herramientas en ToolTip1** valor a una cadena de texto adecuada.  

### <a name="to-remove-a-tooltip-programmatically"></a>Para quitar una información sobre herramientas mediante programación  
  
1. Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a>Para quitar una información sobre herramientas en el diseñador  
  
1. Seleccione el control que muestra la información sobre herramientas.  
  
2. En el **propiedades** ventana, elimine el texto en el **información sobre herramientas en ToolTip1**.  

## <a name="see-also"></a>Vea también

- [Información general sobre el componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Filtrar para cambiar el retardo del componente ToolTip de formularios Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip](tooltip-component-windows-forms.md)
