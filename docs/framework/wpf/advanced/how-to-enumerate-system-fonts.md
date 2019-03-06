---
title: Procedimiento Enumerar fuentes del sistema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: c7e81b5d1b70ba911a0b505219f7977e019038cf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352443"
---
# <a name="how-to-enumerate-system-fonts"></a>Procedimiento Enumerar fuentes del sistema
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo enumerar las fuentes en la colección de fuentes del sistema. El nombre de cada familia de fuentes <xref:System.Windows.Media.FontFamily> en <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> se agrega como un elemento a un cuadro combinado.  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Si varias versiones de la misma familia de fuentes residen en el mismo directorio, el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enumeración fuente devuelve la versión más reciente de la fuente. Si la información de versión no proporciona la resolución, se devuelve la fuente con marca de tiempo más reciente. Si la información de marca de tiempo es equivalente, se devuelve el archivo de fuente que es el primero en orden alfabético.
