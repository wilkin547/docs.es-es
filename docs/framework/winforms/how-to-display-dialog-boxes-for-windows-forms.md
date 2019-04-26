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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802588"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="098eb-102">Procedimiento para mostrar cuadros de diálogo de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="098eb-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="098eb-103">Mostrar un cuadro de diálogo de la misma manera que muestre cualquier otra forma en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="098eb-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="098eb-104">El formulario de inicio se carga automáticamente cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="098eb-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="098eb-105">Para crear un segundo formulario o cuadro de diálogo que aparecen en la aplicación, escribir código para cargar y mostrarla.</span><span class="sxs-lookup"><span data-stu-id="098eb-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="098eb-106">De forma similar, para que el formulario o cuadro de diálogo cuadro desaparecen, escribir código para descargar u ocultarla.</span><span class="sxs-lookup"><span data-stu-id="098eb-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="098eb-107">Para mostrar un cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="098eb-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="098eb-108">Navegue hasta el controlador de eventos con el que desea abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="098eb-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="098eb-109">Esto puede ocurrir cuando se selecciona un comando de menú, cuando se hace clic en un botón o cuando se produce cualquier otro evento.</span><span class="sxs-lookup"><span data-stu-id="098eb-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="098eb-110">En el controlador de eventos, agregue código para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="098eb-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="098eb-111">En este ejemplo, un evento de clic de botón se utiliza para mostrar el cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="098eb-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
