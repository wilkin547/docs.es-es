---
title: Cambiar los bordes del formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739563"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Cómo: Cambiar los bordes de Windows Forms
Puede elegir varios estilos de borde para determinar la apariencia y el comportamiento de sus Windows Forms. Puede cambiar la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> para controlar el comportamiento de cambio de tamaño del formulario. Además, establecer el <xref:System.Windows.Forms.Form.FormBorderStyle%2A> afecta a cómo se muestra la barra de título y qué botones pueden aparecer en ella. Para obtener más información, vea <xref:System.Windows.Forms.FormBorderStyle>.  
  
 Visual Studio es altamente compatible con esta tarea.  
  
 Vea también [Cómo: cambiar los bordes de Windows Forms mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Para establecer el estilo de borde de Windows Forms mediante programación  
  
- Establezca la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> en el estilo que desee. En el ejemplo de código siguiente se establece el estilo de borde del formulario `DlgBx1` en <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     Consulte también [Cómo: crear cuadros de diálogo en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).  
  
     Además, si ha elegido un estilo de borde para el formulario que proporciona botones opcionales para **minimizar** y **maximizar** , puede especificar si desea que uno o ambos botones sean funcionales. Estos botones son útiles si desea controlar estrechamente la experiencia del usuario. Los botones **minimizar** y **maximizar** están habilitados de forma predeterminada y su funcionalidad se manipula a través de la ventana **propiedades** .  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [Introducción a los formularios Windows Forms](getting-started-with-windows-forms.md)
