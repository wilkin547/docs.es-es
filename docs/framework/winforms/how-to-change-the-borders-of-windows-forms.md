---
title: Filtrar Cambiar los bordes de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: f188e14b304970840bfc35a592a445f68f9d7af7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713913"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Procedimiento Cambiar los bordes de Windows Forms
Puede elegir varios estilos de borde para determinar la apariencia y el comportamiento de sus Windows Forms. Puede cambiar la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> para controlar el comportamiento de cambio de tamaño del formulario. Además, establecer el <xref:System.Windows.Forms.Form.FormBorderStyle%2A> afecta a cómo se muestra la barra de título y qué botones pueden aparecer en ella. Para obtener más información, consulta <xref:System.Windows.Forms.FormBorderStyle>.  
  
 Visual Studio es altamente compatible con esta tarea.  
  
 Vea también [Cómo: Cambiar los bordes de formularios de Windows mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Para establecer el estilo de borde de Windows Forms mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> en el estilo que desee. El ejemplo de código siguiente establece el estilo de borde del formulario `DlgBx1` a <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
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
  
     Consulte también [Cómo: Crear cuadros de diálogo en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).  
  
     Además, si ha elegido un estilo de borde para el formulario que proporciona opcional **minimizar** y **maximizar** botones, puede especificar si desea que uno o ambos de estos botones sean funcionales. Estos botones son útiles si desea controlar estrechamente la experiencia del usuario. El **minimizar** y **maximizar** botones están habilitados de forma predeterminada, y su funcionalidad se manipula a través de la **propiedades** ventana.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [Introducción a los formularios Windows Forms](getting-started-with-windows-forms.md)
