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
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="1dc0c-102">Cómo: Mostrar cuadros de diálogo de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1dc0c-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="1dc0c-103">Se muestra un cuadro de diálogo de la misma manera que se muestra cualquier otro formulario en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="1dc0c-104">El formulario de inicio se carga automáticamente cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="1dc0c-105">Para que aparezca un segundo formulario o cuadro de diálogo en la aplicación, escriba código para cargarlo y mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="1dc0c-106">Del mismo modo, para que el formulario o el cuadro de diálogo desaparezcan, escriba código para descargarlo u ocultarlo.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="1dc0c-107">Para mostrar un cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="1dc0c-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="1dc0c-108">Vaya al controlador de eventos con el que desea abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="1dc0c-109">Esto puede suceder cuando se selecciona un comando de menú, cuando se hace clic en un botón o cuando se produce cualquier otro evento.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="1dc0c-110">En el controlador de eventos, agregue código para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1dc0c-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="1dc0c-111">En este ejemplo, se utiliza un evento de clic de botón para mostrar el cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="1dc0c-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
