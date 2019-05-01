---
title: Procedimiento Devolver el resultado de un cuadro de diálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006720"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="fa68d-102">Procedimiento Devolver el resultado de un cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="fa68d-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="fa68d-103">En este ejemplo se muestra cómo recuperar el resultado del cuadro de diálogo para una ventana que se abre mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa68d-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa68d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa68d-104">Example</span></span>  
 <span data-ttu-id="fa68d-105">Antes de que se cierra un cuadro de diálogo, su <xref:System.Windows.Window.DialogResult%2A> se debe establecer la propiedad con un <xref:System.Nullable%601> <xref:System.Boolean> que indica cómo el usuario ha cerrado el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fa68d-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="fa68d-106">Este valor es devuelto por <xref:System.Windows.Window.ShowDialog%2A> para permitir que el código de cliente determinar cómo se cerró el cuadro de diálogo y, por lo tanto, cómo procesar el resultado.</span><span class="sxs-lookup"><span data-stu-id="fa68d-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa68d-107"><xref:System.Windows.Window.DialogResult%2A> solo puede establecerse si se abre una ventana mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa68d-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="fa68d-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa68d-108">.NET Framework Security</span></span>  
 <span data-ttu-id="fa68d-109">Una llamada a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="fa68d-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
