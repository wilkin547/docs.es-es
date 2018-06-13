---
title: Inicialización de elementos de objeto no incluidos en un árbol de objetos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- logical tree [WPF]
- visual tree [WPF]
- elements [WPF], initializing
- initializing elements [WPF]
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
ms.openlocfilehash: 219edcbdb09b4edbd9c5ec31e0def77cce6379bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545537"
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Inicialización de elementos de objeto no incluidos en un árbol de objetos
Algunos aspectos de inicialización de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se fraccionan en procesos que suelen depender de la conexión del elemento con el árbol lógico o visual. En este tema se describen los pasos que pueden ser necesarios para inicializar un elemento que no esté conectado a ninguno de estos árboles.  
  
 
  
## <a name="elements-and-the-logical-tree"></a>Elementos y el árbol lógico  
 Cuando se crea una instancia de una clase de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] en el código, se debe tener en cuenta que varios aspectos de la inicialización de objetos para una clase de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se excluyen deliberadamente del código que se ejecuta al llamar al constructor de la clase. En concreto, en el caso de las clases de control, el constructor no define la mayor parte de la representación visual del control, sino que es la plantilla del control la que define la representación visual. La plantilla puede proceder de diversos orígenes, pero, en la mayoría de casos, se obtiene a partir de estilos de tema. Las plantillas funcionan como enlace en tiempo de ejecución efectivo: la plantilla necesaria no se adjunta al control en cuestión hasta que este está listo para el diseño. Y el control no está listo para el diseño hasta que se adjunta a un árbol lógico que se conecta a una superficie de representación en la raíz. Este elemento de nivel de raíz inicia la representación de todos sus elementos secundarios, como se define en el árbol lógico.  
  
 El árbol visual también participa en este proceso. Tampoco se crean todas las instancias de los elementos que forman parte del árbol visual a través de las plantillas hasta que se conectan.  
  
 Las consecuencias de este comportamiento son que ciertas operaciones que dependen de las características visuales completadas de un elemento requieren pasos adicionales. Un ejemplo sería intentar obtener las características visuales de una clase que se construyó, pero todavía no se ha adjuntado a un árbol. Por ejemplo, si desea llamar a <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> en un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y el objeto visual que se pasa es un elemento no conectado a un árbol, ese elemento no estará completo visualmente hasta que se completen las operaciones de inicialización adicionales.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Uso de BeginInit y EndInit para inicializar el elemento  
 Varias clases en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementar la <xref:System.ComponentModel.ISupportInitialize> interfaz. Usa el <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> y <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> métodos de la interfaz para denotar una región del código que contiene los pasos de inicialización (como configuración de propiedad, los valores que afectan a la representación). Después de <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> se llama en la secuencia, el sistema de diseño puede procesar el elemento y empezar la búsqueda de un estilo implícito.  
  
 Si el elemento está estableciendo las propiedades en un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> clase derivada, a continuación, puede llamar a las versiones de la clase de <xref:System.Windows.FrameworkElement.BeginInit%2A> y <xref:System.Windows.FrameworkElement.EndInit%2A> en lugar de la conversión a <xref:System.ComponentModel.ISupportInitialize>.  
  
### <a name="sample-code"></a>Código de ejemplo  
 El ejemplo siguiente es el código de ejemplo para una aplicación de consola que usa la representación [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] y <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> de un malas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo para ilustrar la colocación correcta de <xref:System.Windows.FrameworkElement.BeginInit%2A> y <xref:System.Windows.FrameworkElement.EndInit%2A> alrededor otro [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] llamadas que ajustar las propiedades que afectan a la representación.  
  
 El ejemplo solo ilustra la función principal. Las funciones `Rasterize` y `Save` (que no se muestran) son funciones de utilidad que se encargan del procesamiento de imágenes y la E/S.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>Vea también  
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
