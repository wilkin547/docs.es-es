---
title: 'Cómo: Mostrar cuadros de diálogo'
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
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181973"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Cómo: Mostrar cuadros de diálogo de formularios Windows Forms
Se muestra un cuadro de diálogo de la misma manera que se muestra cualquier otro formulario en una aplicación. El formulario de inicio se carga automáticamente cuando se ejecuta la aplicación. Para que aparezca un segundo formulario o cuadro de diálogo en la aplicación, escriba código para cargarlo y mostrarlo. Del mismo modo, para que el formulario o el cuadro de diálogo desaparezcan, escriba código para descargarlo u ocultarlo.  
  
### <a name="to-display-a-dialog-box"></a>Para mostrar un cuadro de diálogo  
  
1. Vaya al controlador de eventos con el que desea abrir el cuadro de diálogo. Esto puede suceder cuando se selecciona un comando de menú, cuando se hace clic en un botón o cuando se produce cualquier otro evento.  
  
2. En el controlador de eventos, agregue código para abrir el cuadro de diálogo. En este ejemplo, se utiliza un evento de clic de botón para mostrar el cuadro de diálogo:  
  
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
