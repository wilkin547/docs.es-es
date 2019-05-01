---
title: Procedimiento Establecer el título de una ventana desde una página
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054008"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Procedimiento Establecer el título de una ventana desde una página
En este ejemplo se muestra cómo establecer el título de la ventana en la que un <xref:System.Windows.Controls.Page> se hospeda.  
  
## <a name="example"></a>Ejemplo  
 Una página puede cambiar el título de la ventana que está hospedando estableciendo el <xref:System.Windows.Controls.Page.WindowTitle%2A> propiedad, así:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Establecer el <xref:System.Windows.Controls.Page.Title%2A> propiedad de una página no cambia el valor del título de la ventana. En su lugar, <xref:System.Windows.Controls.Page.Title%2A> especifica el nombre de una entrada de página en el historial de navegación.
