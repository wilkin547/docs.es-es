---
title: Filtrar Obtener todos los de Windows en una aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378844"
---
# <a name="how-to-get-all-windows-in-an-application"></a>Procedimiento Obtener todos los de Windows en una aplicación
En este ejemplo se muestra cómo obtener todos los <xref:System.Windows.Window> objetos en una aplicación.  
  
## <a name="example"></a>Ejemplo  
 Cada crea una instancia <xref:System.Windows.Window> objeto, si es visible o no, se agrega automáticamente a una colección de referencias de la ventana que está administrado por <xref:System.Windows.Application>y se expongan de <xref:System.Windows.Application.Windows%2A>.  
  
 Puede enumerar <xref:System.Windows.Application.Windows%2A> para obtener todas las instancias de windows con el código siguiente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
