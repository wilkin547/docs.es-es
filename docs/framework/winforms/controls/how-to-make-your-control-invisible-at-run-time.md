---
title: 'Cómo: Hacer un control no visible en tiempo de ejecución'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: 51e804c7f01b55ed7504837042b6c32bf47d9405
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532417"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Cómo: Hacer un control no visible en tiempo de ejecución
Hay ocasiones cuando desea crear un control de usuario que sea invisible en tiempo de ejecución. Por ejemplo, un control que es un reloj de alarma podría ser invisible excepto cuando suene la alarma. Esto se consigue fácilmente estableciendo la <xref:System.Windows.Forms.Control.Visible%2A> propiedad. Si el <xref:System.Windows.Forms.Control.Visible%2A> propiedad es `true`, el control aparecerá como normal. Si `false`, se ocultará el control. Aunque todavía puede ejecutar código en el control al invisible, no podrá interactuar con el control a través de la interfaz de usuario. Si desea crear un control invisible que responda a la entrada (por ejemplo, clics del mouse) del usuario, debe crear un control transparente. Para obtener más información, consulte [que proporciona el Control de un fondo transparente](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Para hacer que el control sea invisible en tiempo de ejecución  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Visible%2A> en `false`.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
