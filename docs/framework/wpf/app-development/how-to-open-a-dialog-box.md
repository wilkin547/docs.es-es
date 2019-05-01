---
title: Procedimiento Abrir un cuadro de diálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947711"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="33b18-102">Procedimiento Abrir un cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="33b18-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="33b18-103">En este ejemplo se muestra cómo abrir un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="33b18-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b18-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33b18-104">Example</span></span>  
 <span data-ttu-id="33b18-105">Un cuadro de diálogo es una ventana que se abre al crear una instancia <xref:System.Windows.Window> y llamar a la <xref:System.Windows.Window.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="33b18-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="33b18-106"><xref:System.Windows.Window.ShowDialog%2A> Abre una ventana y no vuelve hasta que se ha cerrado el cuadro de diálogo nuevo.</span><span class="sxs-lookup"><span data-stu-id="33b18-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="33b18-107">Este tipo de ventana también es conocido como un *modal* ventana y restringe la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="33b18-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="33b18-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="33b18-108">.NET Framework Security</span></span>  
 <span data-ttu-id="33b18-109">Una llamada a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="33b18-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b18-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b18-110">See also</span></span>

- [<span data-ttu-id="33b18-111">Volver al resultado de un cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="33b18-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
