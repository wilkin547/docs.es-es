---
title: Filtrar Abra una ventana
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373574"
---
# <a name="how-to-open-a-window"></a>Filtrar Abra una ventana
En este ejemplo se muestra cómo abrir una ventana.  
  
## <a name="example"></a>Ejemplo  
 Se abre una ventana de creación de instancias de <xref:System.Windows.Window> y llamar a la <xref:System.Windows.Window.Show%2A> método. <xref:System.Windows.Window.Show%2A> Abre una ventana y devuelve inmediatamente sin esperar a la nueva ventana Cerrar. Este tipo de ventana también es conocido como un *no modal* ventana y no restringe la entrada del usuario.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Creación de instancias <xref:System.Windows.Window> requiere permiso para llamar a métodos nativos no seguros (vea <xref:System.Windows.Window.%23ctor%2A>).
