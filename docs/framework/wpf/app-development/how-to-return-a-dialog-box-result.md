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
ms.openlocfilehash: d5a1b8cdc0544bfba3f708db40e8b9c593b45b35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-return-a-dialog-box-result"></a>Cómo: devolver un resultado de cuadro de diálogo
Este ejemplo muestra cómo recuperar el resultado de cuadro de diálogo de una ventana que se abre mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Ejemplo  
 Antes de que se cierra un cuadro de diálogo, su <xref:System.Windows.Window.DialogResult%2A> propiedad debe establecerse con un <xref:System.Nullable%601> <xref:System.Boolean> que indica cómo el usuario ha cerrado el cuadro de diálogo. Este valor se devuelve por <xref:System.Windows.Window.ShowDialog%2A> para permitir que el código de cliente determinar cómo se cerró el cuadro de diálogo y, por consiguiente, cómo procesar el resultado.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A>sólo se puede establecer si una ventana se abre mediante una llamada a <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Al llamar a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin ninguna restricción.
