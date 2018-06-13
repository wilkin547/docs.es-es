---
title: 'Cómo: Mostrar cuadros de diálogo de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: a25fe86c4dde1fed69e192956d77615bf2a70402
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537429"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Cómo: Mostrar cuadros de diálogo de formularios Windows Forms
Mostrar un cuadro de diálogo de la misma manera que cualquier otra forma se muestra en una aplicación. El formulario de inicio se carga automáticamente cuando se ejecuta la aplicación. Para crear un segundo formulario o cuadro de diálogo que aparecen en la aplicación, escribir código para cargar y mostrarla. De forma similar, para que el formulario o cuadro de diálogo cuadro desaparecen, escribir código para descargarlo u ocultarlo.  
  
### <a name="to-display-a-dialog-box"></a>Para mostrar un cuadro de diálogo  
  
1.  Navegue hasta el controlador de eventos con el que desea abrir el cuadro de diálogo. Esto puede ocurrir cuando se selecciona un comando de menú, cuando se hace clic en un botón o cuando se produce cualquier otro evento.  
  
2.  En el controlador de eventos, agregue código para abrir el cuadro de diálogo. En este ejemplo, se utiliza un evento de clic de botón para mostrar el cuadro de diálogo:  
  
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
