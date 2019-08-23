---
title: Procedimiento Devolver el resultado de un cuadro de diálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968234"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="1ff99-102">Procedimiento Devolver el resultado de un cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="1ff99-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="1ff99-103">En este ejemplo se muestra cómo recuperar el resultado del cuadro de diálogo para una ventana que <xref:System.Windows.Window.ShowDialog%2A>se abre mediante una llamada a.</span><span class="sxs-lookup"><span data-stu-id="1ff99-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ff99-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ff99-104">Example</span></span>  
 <span data-ttu-id="1ff99-105">Antes de que se cierre un cuadro de <xref:System.Windows.Window.DialogResult%2A> diálogo, su propiedad se debe <xref:System.Nullable%601> establecer con un <xref:System.Boolean> valor de que indique cómo el usuario ha cerrado el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1ff99-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="1ff99-106">Devuelve este valor <xref:System.Windows.Window.ShowDialog%2A> para permitir que el código de cliente determine cómo se cerró el cuadro de diálogo y, por consiguiente, cómo procesar el resultado.</span><span class="sxs-lookup"><span data-stu-id="1ff99-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ff99-107"><xref:System.Windows.Window.DialogResult%2A>solo se puede establecer si se ha abierto una ventana mediante <xref:System.Windows.Window.ShowDialog%2A>una llamada a.</span><span class="sxs-lookup"><span data-stu-id="1ff99-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="1ff99-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1ff99-108">.NET Framework Security</span></span>  
 <span data-ttu-id="1ff99-109">La <xref:System.Windows.Window.ShowDialog%2A> llamada requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="1ff99-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
