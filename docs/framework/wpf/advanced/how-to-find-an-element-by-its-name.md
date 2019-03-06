---
title: Filtrar Buscar un elemento por su nombre
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: 7405f9ba8db5d4db0ce35ca250f13e456685f39b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351062"
---
# <a name="how-to-find-an-element-by-its-name"></a>Filtrar Buscar un elemento por su nombre
En este ejemplo se describe cómo usar el <xref:System.Windows.FrameworkElement.FindName%2A> método para buscar un elemento por su <xref:System.Windows.FrameworkElement.Name%2A> valor.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el método para buscar un elemento determinado por su nombre se escribe como el controlador de eventos de un botón. `stackPanel` es el <xref:System.Windows.FrameworkElement.Name%2A> de la raíz <xref:System.Windows.FrameworkElement> que se está buscando, y el método de ejemplo, a continuación, indica visualmente el elemento encontrado convirtiéndola como <xref:System.Windows.Controls.TextBlock> y cambiar uno de los <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] propiedades.  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
