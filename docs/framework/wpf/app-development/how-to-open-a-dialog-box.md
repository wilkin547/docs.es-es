---
title: "Cómo: abrir un cuadro de diálogo"
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
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d318f35f8f009f0f2c77210ca8b6b29bedfb7619
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-dialog-box"></a>Cómo: abrir un cuadro de diálogo
Este ejemplo muestra cómo abrir un cuadro de diálogo.  
  
## <a name="example"></a>Ejemplo  
 Un cuadro de diálogo es una ventana que se abre la creación de instancias <xref:System.Windows.Window> y llamar a la <xref:System.Windows.Window.ShowDialog%2A> método. <xref:System.Windows.Window.ShowDialog%2A>Abre una ventana y no vuelve hasta que se ha cerrado el cuadro de diálogo nuevo. Este tipo de ventana también se denomina es un *modal* ventana y restringe proporcionados por el usuario.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Al llamar a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin ninguna restricción.  
  
## <a name="see-also"></a>Vea también  
 [Volver al resultado de un cuadro de diálogo](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
