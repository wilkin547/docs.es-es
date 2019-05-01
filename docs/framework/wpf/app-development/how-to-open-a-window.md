---
title: Procedimiento Abrir una ventana
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947685"
---
# <a name="how-to-open-a-window"></a>Procedimiento Abrir una ventana
En este ejemplo se muestra cómo abrir una ventana.  
  
## <a name="example"></a>Ejemplo  
 Se abre una ventana de creación de instancias de <xref:System.Windows.Window> y llamar a la <xref:System.Windows.Window.Show%2A> método. <xref:System.Windows.Window.Show%2A> Abre una ventana y devuelve inmediatamente sin esperar a la nueva ventana Cerrar. Este tipo de ventana también es conocido como un *no modal* ventana y no restringe la entrada del usuario.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Creación de instancias <xref:System.Windows.Window> requiere permiso para llamar a métodos nativos no seguros (vea <xref:System.Windows.Window.%23ctor%2A>).
