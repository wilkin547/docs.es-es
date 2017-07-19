---
title: "How to: Display Dialog Boxes for Windows Forms | Microsoft Docs"
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
  - "Windows Forms, displaying"
  - "Windows Forms dialog boxes, displaying"
  - "Windows Forms, calling one form from another"
  - "dialog boxes, displaying for Windows Forms"
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Display Dialog Boxes for Windows Forms
Los cuadros de diálogo se muestran de la misma forma que cualquier otro formulario de una aplicación.  El formulario de inicio se cargará automáticamente cuando se ejecute la aplicación.  Para hacer que aparezca en la aplicación un segundo formulario o cuadro de diálogo, escriba código para cargarlo y mostrarlo.  Del mismo modo, para hacer que desaparezca el formulario o cuadro de diálogo deberá escribir código para descargarlo u ocultarlo.  
  
### Para mostrar un cuadro de diálogo  
  
1.  Navegue hasta el controlador de eventos con el que desea abrir el cuadro de diálogo.  Esto puede suceder cuando se selecciona un comando de menú, cuando se hace clic en un botón o cuando sucede cualquier otro evento.  
  
2.  En el controlador de eventos, agregue código para abrir el cuadro de diálogo.  En este ejemplo, se utiliza un evento clic de botón para mostrar el cuadro de diálogo:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```