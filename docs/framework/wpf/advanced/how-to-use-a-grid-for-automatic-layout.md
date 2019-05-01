---
title: Procedimiento Usar una cuadrícula para el diseño automático
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052409"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Procedimiento Usar una cuadrícula para el diseño automático
En este ejemplo se describe cómo usar una cuadrícula en el enfoque de diseño automático para crear una aplicación localizable.  
  
 Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento. A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto. En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario. Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste. El enfoque para escribir aplicaciones que pueden ser más fácil cambiar el tamaño y posición se denomina `auto layout`.  
  
 La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra cómo utilizar una cuadrícula para colocar algunos botones y texto. Tenga en cuenta que el alto y ancho de las celdas están establecidos en `Auto`; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen. Dado que el <xref:System.Windows.Controls.Grid> elemento puede ajustarse a su contenido puede ser útil al tomar el enfoque de diseño automático para diseñar aplicaciones que se pueden localizar.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar una cuadrícula.  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra la salida del ejemplo de código.  
  
 ![Ejemplo de cuadrícula](./media/glob-grid.png "glob_grid")  
Cuadrícula  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el uso del diseño automático](use-automatic-layout-overview.md)
- [Usar el diseño automático para crear un botón](how-to-use-automatic-layout-to-create-a-button.md)
