---
title: Procedimiento para mostrar cuadros de diálogo de formularios Windows Forms
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
ms.openlocfilehash: b99f2273dae88faf86448da6e1d2986a83803abf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773823"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Procedimiento para mostrar cuadros de diálogo de formularios Windows Forms
Mostrar un cuadro de diálogo de la misma manera que muestre cualquier otra forma en una aplicación. El formulario de inicio se carga automáticamente cuando se ejecuta la aplicación. Para crear un segundo formulario o cuadro de diálogo que aparecen en la aplicación, escribir código para cargar y mostrarla. De forma similar, para que el formulario o cuadro de diálogo cuadro desaparecen, escribir código para descargar u ocultarla.  
  
### <a name="to-display-a-dialog-box"></a>Para mostrar un cuadro de diálogo  
  
1. Navegue hasta el controlador de eventos con el que desea abrir el cuadro de diálogo. Esto puede ocurrir cuando se selecciona un comando de menú, cuando se hace clic en un botón o cuando se produce cualquier otro evento.  
  
2. En el controlador de eventos, agregue código para abrir el cuadro de diálogo. En este ejemplo, un evento de clic de botón se utiliza para mostrar el cuadro de diálogo:  
  
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
