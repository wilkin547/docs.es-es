---
title: Procedimiento Hacer que el Control Invisible en tiempo de ejecución
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
ms.openlocfilehash: 00f352e0b2c0582c45710f7e5a26e68ab7fbd944
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597802"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>Procedimiento Hacer que el Control Invisible en tiempo de ejecución
Hay veces cuando desee crear un control de usuario que sea invisible en tiempo de ejecución. Por ejemplo, un control que sea un reloj despertador podría ser invisible excepto cuando suene la alarma. Esto se consigue estableciendo la <xref:System.Windows.Forms.Control.Visible%2A> propiedad. Si el <xref:System.Windows.Forms.Control.Visible%2A> propiedad es `true`, el control aparecerá con normalidad. Si `false`, se ocultará el control. Aunque todavía puede ejecutar código en el control aunque sea invisible, no podrá interactuar con el control a través de la interfaz de usuario. Si desea crear un control invisible que responda a los usuarios de entrada (por ejemplo, clics del mouse), debe crear un control transparente. Para obtener más información, consulte [proporcionar un fondo transparente Control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>Para que el control sea invisible en tiempo de ejecución  
  
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
- <xref:System.Windows.Forms.Control.Visible%2A>
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [Cómo: Proporcionar un fondo transparente a un Control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
