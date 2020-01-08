---
title: Información general sobre topologías de navegación
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: 5679bac06b87b3c4e50cbc4a238d7daf3e33a564
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636281"
---
# <a name="navigation-topologies-overview"></a>Información general sobre topologías de navegación
<a name="introduction"></a>Esta información general proporciona una introducción a las topologías de navegación en WPF. Posteriormente, se tratan tres topologías de navegación comunes y se incluyen ejemplos de estas.  
  
> [!NOTE]
> Antes de leer este tema, debe estar familiarizado con el concepto de navegación estructurada en WPF mediante funciones de página. Para obtener más información sobre ambos temas, consulte [información general sobre la navegación estructurada](structured-navigation-overview.md).  
  
 Este tema contiene las siguientes secciones:  
  
- [Topologías de navegación](#Navigation_Topologies)  
  
- [Topologías de navegación estructurada](#Structured_Navigation_Topologies)  
  
- [Navegación mediante una topología lineal fija](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [Navegación dinámica mediante una topología jerárquica fija](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [Navegación mediante una topología generada dinámicamente](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a>Topologías de navegación  
 En WPF, la navegación normalmente consta de páginas (<xref:System.Windows.Controls.Page>) con hipervínculos (<xref:System.Windows.Documents.Hyperlink>) que navegan a otras páginas al hacer clic en ellas. Las páginas a las que se navega se identifican mediante identificadores uniformes de recursos (URI) (consulte [pack uri en WPF](pack-uris-in-wpf.md)). Considere el siguiente ejemplo sencillo que muestra páginas, hipervínculos e identificadores uniformes de recursos (URI):  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 Estas páginas están organizadas en una *topología de navegación* cuya estructura viene determinada por el modo en que puede desplazarse entre las páginas. Esta topología de navegación concreta es adecuada en escenarios simples, aunque la navegación puede exigir topologías más complejas, algunas de las cuales solo pueden definirse cuando se ejecuta una aplicación.  
  
 En este tema se tratan tres topologías de navegación comunes: *lineal fija*, *fija jerárquica*y *generada dinámicamente*. Cada topología de navegación se muestra con un ejemplo que tiene un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] como el que se muestra en la ilustración siguiente:  
  
 ![Páginas de tareas con elementos de datos y botones de navegación.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a>Topologías de navegación estructurada  
 Hay dos tipos generales de topologías de navegación:  
  
- **Topología fija**: se define en tiempo de compilación y no cambia en tiempo de ejecución. Las topologías fijas son útiles para la navegación a través de una secuencia fija de páginas en un orden lineal o jerárquico.  
  
- **Topología dinámica**: se define en tiempo de ejecución en función de la entrada que se recopila del usuario, la aplicación o el sistema. Las topologías dinámicas son útiles cuando las páginas pueden navegarse en secuencias diferentes.  
  
 Aunque es posible crear topologías de navegación mediante páginas, los ejemplos usan funciones de página porque proporcionan compatibilidad adicional que simplifica la compatibilidad para pasar y devolver los datos a través de las páginas de una topología.  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a>Navegación mediante una topología lineal fija  
 Una topología lineal fija se parece a la estructura de un asistente que tiene una o más páginas por las que se navega en una secuencia fija. En la ilustración siguiente se muestra la estructura de alto nivel y el flujo de un asistente con una topología lineal fija:  
  
 ![Diagrama que muestra una topología lineal fija.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 Los comportamientos típicos de la navegación mediante una topología lineal fija son los siguientes:  
  
- Navegación desde la página de llamada a una página de inicio que inicializa el asistente y dirige a la primera página del asistente. No se requiere una página de iniciador (una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]menos <xref:System.Windows.Navigation.PageFunction%601>), ya que una página que llama puede llamar directamente a la primera página del asistente. Sin embargo, el uso de una página de inicio puede simplificar la inicialización del asistente, especialmente si es compleja.  
  
- Los usuarios pueden navegar entre páginas mediante los botones Atrás y Adelante (o hipervínculos).  
  
- Los usuarios pueden navegar entre páginas mediante el diario.  
  
- Los usuarios pueden cancelar al asistente desde cualquier página del asistente presionando el botón Cancelar.  
  
- Los usuarios pueden aceptar al asistente en la última página de este presionando el botón Finalizar.  
  
- Si se cancela un asistente, este devuelve un resultado adecuado y no devuelve ningún dato.  
  
- Si un usuario acepta un asistente, este devuelve un resultado adecuado y los datos que recopiló.  
  
- Cuando se completa el asistente (se acepta o se cancela), las páginas que componen el asistente se quitan del diario. Esto mantiene cada instancia del asistente aislada, lo que evita posibles anomalías de los datos o el estado.  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a>Navegación dinámica mediante una topología jerárquica fija  
 En algunas aplicaciones, las páginas permiten la navegación a dos o más páginas, como se muestra en la ilustración siguiente: 
  
 ![Diagrama que muestra una página que puede navegar a varias páginas.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 Esta estructura se conoce como topología jerárquica fija, y la secuencia en la que se recorre la jerarquía a menudo la determinan en tiempo de ejecución la aplicación o el usuario. En tiempo de ejecución, cada página de la jerarquía que permite la navegación a dos o más páginas recopila los datos necesarios para determinar a qué página se debe navegar. En la ilustración siguiente se muestra una de varias secuencias de navegación posibles basadas en la ilustración anterior:  
  
 ![Diagrama que muestra una posible secuencia de navegación.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 Aunque la secuencia en la que se navega por las páginas de una estructura jerárquica fija se determina en tiempo de ejecución, la experiencia del usuario es la misma que la de una topología lineal fija:  
  
- Navegación desde la página de llamada a una página de inicio que inicializa el asistente y dirige a la primera página del asistente. No se requiere una página de iniciador (una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]menos <xref:System.Windows.Navigation.PageFunction%601>), ya que una página que llama puede llamar directamente a la primera página del asistente. Sin embargo, el uso de una página de inicio puede simplificar la inicialización del asistente, especialmente si es compleja.  
  
- Los usuarios pueden navegar entre páginas mediante los botones Atrás y Adelante (o hipervínculos).  
  
- Los usuarios pueden navegar entre páginas mediante el diario.  
  
- Los usuarios pueden cambiar la secuencia de exploración si navegan hacia atrás a través del diario.  
  
- Los usuarios pueden cancelar al asistente desde cualquier página del asistente presionando el botón Cancelar.  
  
- Los usuarios pueden aceptar al asistente en la última página de este presionando el botón Finalizar.  
  
- Si se cancela un asistente, este devuelve un resultado adecuado y no devuelve ningún dato.  
  
- Si un usuario acepta un asistente, este devuelve un resultado adecuado y los datos que recopiló.  
  
- Cuando se completa el asistente (se acepta o se cancela), las páginas que componen el asistente se quitan del diario. Esto mantiene cada instancia del asistente aislada, lo que evita posibles anomalías de los datos o el estado.  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a>Navegación mediante una topología generada dinámicamente  
 En algunas aplicaciones, la secuencia en la que se navega por dos o más páginas solo la puede determinar en tiempo de ejecución el usuario, la aplicación o los datos externos. En la ilustración siguiente se muestra un conjunto de páginas con una secuencia de navegación indeterminada:  
  
 ![Un conjunto de páginas con una secuencia de navegación indeterminada.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 En la ilustración siguiente se muestra una secuencia de navegación elegida por el usuario en tiempo de ejecución:  
  
 ![Diagrama que muestra una secuencia de navegación elegida en tiempo de ejecución.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 La secuencia de navegación se conoce como topología generada dinámicamente. Para el usuario, al igual que con las otras topologías de navegación, la experiencia del usuario es la misma que en las topologías anteriores:  
  
- Navegación desde la página de llamada a una página de inicio que inicializa el asistente y dirige a la primera página del asistente. No se requiere una página de iniciador (una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]menos <xref:System.Windows.Navigation.PageFunction%601>), ya que una página que llama puede llamar directamente a la primera página del asistente. Sin embargo, el uso de una página de inicio puede simplificar la inicialización del asistente, especialmente si es compleja.  
  
- Los usuarios pueden navegar entre páginas mediante los botones Atrás y Adelante (o hipervínculos).  
  
- Los usuarios pueden navegar entre páginas mediante el diario.  
  
- Los usuarios pueden cancelar al asistente desde cualquier página del asistente presionando el botón Cancelar.  
  
- Los usuarios pueden aceptar al asistente en la última página de este presionando el botón Finalizar.  
  
- Si se cancela un asistente, este devuelve un resultado adecuado y no devuelve ningún dato.  
  
- Si un usuario acepta un asistente, este devuelve un resultado adecuado y los datos que recopiló.  
  
- Cuando se completa el asistente (se acepta o se cancela), las páginas que componen el asistente se quitan del diario. Esto mantiene cada instancia del asistente aislada, lo que evita posibles anomalías de los datos o el estado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Información general sobre la navegación estructurada](structured-navigation-overview.md)
