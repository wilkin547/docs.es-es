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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084992"
---
# <a name="how-to-open-a-dialog-box"></a>Procedimiento Abrir un cuadro de diálogo
En este ejemplo se muestra cómo abrir un cuadro de diálogo.  
  
## <a name="example"></a>Ejemplo  
 Un cuadro de diálogo es una ventana que se abre al crear una instancia <xref:System.Windows.Window> y llamar a la <xref:System.Windows.Window.ShowDialog%2A> método. <xref:System.Windows.Window.ShowDialog%2A> Abre una ventana y no vuelve hasta que se ha cerrado el cuadro de diálogo nuevo. Este tipo de ventana también es conocido como un *modal* ventana y restringe la entrada del usuario.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Una llamada a <xref:System.Windows.Window.ShowDialog%2A> requiere el permiso para usar todas las ventanas y eventos de entrada de usuario sin restricciones.  
  
## <a name="see-also"></a>Vea también

- [Volver al resultado de un cuadro de diálogo](how-to-return-a-dialog-box-result.md)
