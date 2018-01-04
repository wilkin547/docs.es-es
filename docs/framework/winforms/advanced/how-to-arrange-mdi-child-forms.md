---
title: "Cómo: Organizar formularios MDI secundarios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a0a32f6a97e02db8e395db504f36bb5270b195c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-arrange-mdi-child-forms"></a>Cómo: Organizar formularios MDI secundarios
A menudo, las aplicaciones van a tener comandos de menú para acciones (como Mosaico, Cascada y Organizar) que controlan el diseño de los formularios secundarios MDI abiertos. Puede usar el método <xref:System.Windows.Forms.Form.LayoutMdi%2A> con uno de los valores de enumeración de <xref:System.Windows.Forms.MdiLayout> para reorganizar los formularios secundarios en un formulario primario MDI.  
  
 Los valores de la enumeración de <xref:System.Windows.Forms.MdiLayout> muestran los formularios secundarios en cascada, en mosaico horizontal o vertical o como iconos de formulario secundario dispuestos a lo largo de la parte inferior del formulario MDI. Estos valores no tienen el mismo efecto que los comandos de Windows **ventanas en cascada**, **mostrar ventanas en paralelo**, **mostrar ventanas apiladas**, y **mostrar el escritorio** , respectivamente.  
  
 Con frecuencia, estos métodos se usan como los controladores de eventos a los que llama el evento <xref:System.Windows.Forms.Control.Click> de un elemento de menú. De este modo, un elemento de menú con el texto "Ventanas en cascada" puede tener el efecto deseado en las ventanas secundarias de MDI.  
  
### <a name="to-arrange-child-forms"></a>Para organizar los formularios secundarios  
  
1.  En un método, use el método <xref:System.Windows.Forms.Form.LayoutMdi%2A> para establecer la enumeración <xref:System.Windows.Forms.MdiLayout> para el formulario primario MDI. En el siguiente ejemplo se usa el valor de enumeración de <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> para las ventanas secundarias del formulario primario MDI (`Form1`). La enumeración se utiliza en el código durante el controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos de la **ventanas en cascada** elemento de menú.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  Las ventanas también se pueden colocar en mosaico u organizarse como iconos si se cambia el valor de enumeración de <xref:System.Windows.Forms.MdiLayout> utilizado.  
  
2.  Si usa Visual C#, incluya el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones de interfaz de múltiples documentos (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Determinar el formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
