---
title: "How to: Change the Borders of Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, changing the borders"
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Change the Borders of Windows Forms
Puede elegir varios estilos de borde para determinar la apariencia y el comportamiento de sus Windows Forms.  Puede cambiar la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> para controlar el comportamiento de cambio de tamaño del formulario.  Además, establecer el <xref:System.Windows.Forms.Form.FormBorderStyle%2A> afecta a cómo se muestra la barra de título y qué botones pueden aparecer en ella.  Para obtener más información, vea <xref:System.Windows.Forms.FormBorderStyle>.  
  
 Hay una amplia compatibilidad para esta tarea en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
 Consulte también [Cómo: Cambiar los bordes de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/yettzh3e%20\(v=vs.110\)).  
  
### Para establecer el estilo de borde de Windows Forms mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> en el estilo que desee.  En el ejemplo de código siguiente se establece el estilo de borde del formulario `DlgBx1`  en <xref:System.Windows.Forms.FormBorderStyle>.  
  
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
  
     Consulte también [Cómo: Crear cuadros de diálogo en tiempo de diseño](http://msdn.microsoft.com/library/55cz5x2c%20\(v=vs.110\)).  
  
     Además, si ha elegido un estilo de borde para el formulario que proporciona botones **Minimizar** y **Maximizar** opcionales, puede especificar si desea que uno o ambos botones sean funcionales.  Estos botones son útiles si desea controlar estrechamente la experiencia del usuario.  Los botones **Minimizar** y **Maximizar** están habilitados de forma predeterminada, y su funcionalidad se manipula mediante la ventana **Propiedades**.  
  
## Vea también  
 <xref:System.Windows.Forms.FormBorderStyle>   
 <xref:System.Windows.Forms.FormBorderStyle>   
 [Getting Started with Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)