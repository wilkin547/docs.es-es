---
title: 'Cómo: establecer el título de una ventana de una página'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: e69812b59783717b7b9c832d4e8ab01ab42827c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Cómo: establecer el título de una ventana de una página
Este ejemplo muestra cómo establecer el título de la ventana en la que un <xref:System.Windows.Controls.Page> se hospeda.  
  
## <a name="example"></a>Ejemplo  
 Una página puede cambiar el título de la ventana que se hospeda estableciendo la <xref:System.Windows.Controls.Page.WindowTitle%2A> propiedad, así:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Establecer el <xref:System.Windows.Controls.Page.Title%2A> propiedad de una página no cambia el valor de título de la ventana. En su lugar, <xref:System.Windows.Controls.Page.Title%2A> especifica el nombre de una entrada de página en el historial de navegación.
