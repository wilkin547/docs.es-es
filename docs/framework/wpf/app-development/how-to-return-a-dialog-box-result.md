---
title: "Cómo: devolver un resultado de cuadro de diálogo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8133ffa7be9cb4e0600fc2681402d5e0f7471c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="ae177-102">Cómo: devolver un resultado de cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="ae177-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="ae177-103">Este ejemplo muestra cómo recuperar el resultado de cuadro de diálogo de una ventana que se abre mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae177-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae177-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae177-104">Example</span></span>  
 <span data-ttu-id="ae177-105">Antes de que se cierra un cuadro de diálogo, su <xref:System.Windows.Window.DialogResult%2A> propiedad debe establecerse con un <xref:System.Nullable%601> <xref:System.Boolean> que indica cómo el usuario ha cerrado el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae177-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="ae177-106">Este valor se devuelve por <xref:System.Windows.Window.ShowDialog%2A> para permitir que el código de cliente determinar cómo se cerró el cuadro de diálogo y, por consiguiente, cómo procesar el resultado.</span><span class="sxs-lookup"><span data-stu-id="ae177-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae177-107"><xref:System.Windows.Window.DialogResult%2A>sólo se puede establecer si una ventana se abre mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae177-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="ae177-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ae177-108">.NET Framework Security</span></span>  
 <span data-ttu-id="ae177-109">Al llamar a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin ninguna restricción.</span><span class="sxs-lookup"><span data-stu-id="ae177-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
