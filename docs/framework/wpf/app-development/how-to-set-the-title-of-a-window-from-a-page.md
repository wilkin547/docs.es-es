---
title: Procedimiento Establecer el título de una ventana desde una página
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940785"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Procedimiento Establecer el título de una ventana desde una página
Este ejemplo muestra cómo establecer el título de la ventana en la que se <xref:System.Windows.Controls.Page> hospeda un.  
  
## <a name="example"></a>Ejemplo  
 Una página puede cambiar el título de la ventana que la hospeda mediante el establecimiento de <xref:System.Windows.Controls.Page.WindowTitle%2A> la propiedad, de la siguiente manera:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> Al establecer <xref:System.Windows.Controls.Page.Title%2A> la propiedad de una página, no se cambia el valor del título de la ventana. En su lugar <xref:System.Windows.Controls.Page.Title%2A> , especifica el nombre de una entrada de página en el historial de navegación.
