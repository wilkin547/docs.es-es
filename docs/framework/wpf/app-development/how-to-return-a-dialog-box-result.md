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
# <a name="how-to-return-a-dialog-box-result"></a>Procedimiento Devolver el resultado de un cuadro de diálogo
En este ejemplo se muestra cómo recuperar el resultado del cuadro de diálogo para una ventana que se abre mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Ejemplo  
 Antes de que se cierra un cuadro de diálogo, su <xref:System.Windows.Window.DialogResult%2A> se debe establecer la propiedad con un <xref:System.Nullable%601> <xref:System.Boolean> que indica cómo el usuario ha cerrado el cuadro de diálogo. Este valor es devuelto por <xref:System.Windows.Window.ShowDialog%2A> para permitir que el código de cliente determinar cómo se cerró el cuadro de diálogo y, por lo tanto, cómo procesar el resultado.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> solo puede establecerse si se abre una ventana mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Una llamada a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin restricciones.
