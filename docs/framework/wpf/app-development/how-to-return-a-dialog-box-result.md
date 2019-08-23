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
# <a name="how-to-return-a-dialog-box-result"></a>Procedimiento Devolver el resultado de un cuadro de diálogo
En este ejemplo se muestra cómo recuperar el resultado del cuadro de diálogo para una ventana que <xref:System.Windows.Window.ShowDialog%2A>se abre mediante una llamada a.  
  
## <a name="example"></a>Ejemplo  
 Antes de que se cierre un cuadro de <xref:System.Windows.Window.DialogResult%2A> diálogo, su propiedad se debe <xref:System.Nullable%601> establecer con un <xref:System.Boolean> valor de que indique cómo el usuario ha cerrado el cuadro de diálogo. Devuelve este valor <xref:System.Windows.Window.ShowDialog%2A> para permitir que el código de cliente determine cómo se cerró el cuadro de diálogo y, por consiguiente, cómo procesar el resultado.  
  
> [!NOTE]
> <xref:System.Windows.Window.DialogResult%2A>solo se puede establecer si se ha abierto una ventana mediante <xref:System.Windows.Window.ShowDialog%2A>una llamada a.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 La <xref:System.Windows.Window.ShowDialog%2A> llamada requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin restricciones.
