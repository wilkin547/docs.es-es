---
title: Procedimiento Usar el diseño automático para crear un botón
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 8eb1e93dd87c210812c9b7758c744a616ef2d862
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052396"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Procedimiento Usar el diseño automático para crear un botón
En este ejemplo se describe cómo usar el enfoque de diseño automático para crear un botón en una aplicación localizable.  
  
 Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento. A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto. En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario. Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste. El enfoque para escribir aplicaciones que pueden ser más fácil cambiar el tamaño y la posición se denomina `automatic layout`.  
  
## <a name="example"></a>Ejemplo  

Las dos siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos crean aplicaciones que crean instancias de un botón; una con texto en inglés y otra con texto en español. Observe que el código es el mismo, salvo para el texto; el botón se ajusta para adaptarse al texto.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 El gráfico siguiente muestra la salida de los ejemplos de código con los botones de tamaño variable automática:
  
 ![El mismo botón con texto en diferentes idiomas](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el uso del diseño automático](use-automatic-layout-overview.md)
- [Usar una cuadrícula para el diseño automático](how-to-use-a-grid-for-automatic-layout.md)
