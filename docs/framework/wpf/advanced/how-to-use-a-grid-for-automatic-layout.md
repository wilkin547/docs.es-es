---
title: "Cómo: Usar una cuadrícula para el diseño automático"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d18563c44381a276d15996dff3f9552c46833b4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Cómo: Usar una cuadrícula para el diseño automático
En este ejemplo se describe cómo usar una cuadrícula en el enfoque de diseño automático para crear una aplicación localizable.  
  
 Localización de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso lento. A menudo, los localizadores tienen que cambiar el tamaño y la posición de los elementos, además de traducir el texto. En el pasado cada idioma que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ha adaptado para el ajuste necesario. Ahora con las capacidades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede diseñar elementos que reducen la necesidad de ajuste. El enfoque para escribir aplicaciones que pueden resultar más fácil volver a tamaño y cambia de posición se denomina `auto layout`.  
  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra cómo utilizar una cuadrícula para colocar algunos botones y texto. Observe que el alto y ancho de las celdas se establecen en `Auto`; por lo tanto, la celda que contiene el botón con una imagen se ajusta para que quepa la imagen. Dado que el <xref:System.Windows.Controls.Grid> elemento puede ajustar a su contenido puede ser útil cuando se toma el enfoque de diseño automático al diseño de aplicaciones que se pueden localizar.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar una cuadrícula.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra la salida del ejemplo de código.  
  
 ![Ejemplo de cuadrícula](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Cuadrícula  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el uso del diseño automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Usar el diseño automático para crear un botón](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
