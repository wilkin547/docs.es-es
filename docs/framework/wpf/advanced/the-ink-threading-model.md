---
title: Modelo de subprocesamiento de entrada manuscrita
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: cc0ff8a2345bd945dd2fffdfda80f00e1ab99c67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547884"
---
# <a name="the-ink-threading-model"></a>Modelo de subprocesamiento de entrada manuscrita
Una de las ventajas de la tinta en un Tablet PC es que asemeja mucho a escribir con un lápiz normal y el papel.  Para lograr esto, el lápiz de tablet PC recopila datos de entrada a una velocidad mucho más alta que un mouse y representa la entrada de lápiz mientras el usuario escribe.  Subproceso de interfaz (UI) de usuario de la aplicación no es suficiente para recopilar los datos del lápiz y tinta de representación, porque puede quedarse bloqueado.  Para solucionarlo, un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación usa dos subprocesos adicionales cuando un usuario escribe la entrada de lápiz.  
  
 En la lista siguiente se describe los subprocesos que toman parte en la recopilación y representación de entrada de lápiz digital:  
  
-   Subproceso del lápiz - el subproceso que toma como entrado de lápiz.  (En realidad, se trata de un grupo de subprocesos, pero este tema hace referencia a él como un subproceso del lápiz.)  
  
-   Subproceso de interfaz de usuario de la aplicación: el subproceso que controla la interfaz de usuario de la aplicación.  
  
-   Subproceso de representación dinámica - el subproceso que representa la entrada de lápiz mientras el usuario dibuja un trazo. El subproceso de representación dinámica es diferente del subproceso que representa otros elementos de interfaz de usuario para la aplicación, como se mencionó en la ventana Presentation Foundation [modelo de subprocesamiento](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
 El modelo de escritura a mano es el mismo independientemente de la aplicación utilice la <xref:System.Windows.Controls.InkCanvas> o un control personalizado similar a la de [crear un Control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  Aunque en este tema se describe el subprocesamiento en términos de la <xref:System.Windows.Controls.InkCanvas>, los mismos conceptos que se aplican cuando se crea un control personalizado.  
  
## <a name="threading-overview"></a>Información general de subprocesos  
 El siguiente diagrama ilustra el modelo de subprocesos cuando un usuario dibuja un trazo:  
  
 ![Modelo de subprocesos mientras se dibuja un trazo. ] (../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1.  Acciones que se producen mientras el usuario dibuja el trazo  
  
    1.  Cuando el usuario dibuja un trazo, los puntos del lápiz se enciende el subproceso del lápiz.  Lápiz complementos, incluido el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, acepte los puntos del lápiz en el subproceso del lápiz y tienen la oportunidad de modificarlos antes de la <xref:System.Windows.Controls.InkCanvas> reciben.  
  
    2.  El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> representa los puntos del lápiz en el subproceso de representación dinámica. Esto sucede al mismo tiempo que el paso anterior.  
  
    3.  El <xref:System.Windows.Controls.InkCanvas> recibe los puntos del lápiz en el subproceso de interfaz de usuario.  
  
2.  Acciones que se producen después de que el usuario finaliza el trazo  
  
    1.  Cuando el usuario termina de dibujar el trazo del <xref:System.Windows.Controls.InkCanvas> crea un <xref:System.Windows.Ink.Stroke> objeto y lo agrega a la <xref:System.Windows.Controls.InkPresenter>, que representa de forma estática.  
  
    2.  Las alertas de subproceso de interfaz de usuario la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> que el trazo se representa estáticamente, por lo que el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> quita su representación visual del trazo.  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>Colección de tinta y complementos de lápiz  
 Cada <xref:System.Windows.UIElement> tiene un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  El <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objetos en el <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> reciben y pueden modificar los puntos del lápiz en el subproceso del lápiz. El <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objetos reciben los puntos del lápiz según el orden de la <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  
  
 El diagrama siguiente ilustra la situación hipotética donde la <xref:System.Windows.UIElement.StylusPlugIns%2A> colección de un <xref:System.Windows.UIElement> contiene `stylusPlugin1`, un <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, y `stylusPlugin2`, en ese orden.  
  
 ![Orden de complementos de lápiz afecta a la salida. ] (../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 En el diagrama anterior, produzca el siguiente comportamiento:  
  
1.  `StylusPlugin1` modifica los valores de x e y.  
  
2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> recibe los puntos del lápiz modificados y los representa en el subproceso de representación dinámica.  
  
3.  `StylusPlugin2` recibe los puntos del lápiz modificados y más modifica los valores de x e y.  
  
4.  La aplicación recopila los puntos del lápiz y, cuando el usuario finaliza el trazo, lo representa estáticamente.  
  
 Suponga que `stylusPlugin1` restringe los puntos del lápiz a un rectángulo y `stylusPlugin2` traduce los puntos del lápiz a la derecha.  En el escenario anterior, el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> recibe los puntos del lápiz restringidos, pero no los puntos del lápiz traducidos.  Cuando el usuario dibuja el trazo, el trazo se representa dentro de los límites del rectángulo, pero no aparece el trazo que se deben traducir hasta que el usuario levanta el lápiz.  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>Realizar operaciones con un lápiz de complemento en el subproceso de interfaz de usuario  
 Porque no se puede realizar la prueba de posicionamiento precisa en el subproceso del lápiz, algunos elementos en ocasiones pueden recibir la entrada del lápiz dirigida a otros elementos. Si necesita asegurarse de que la entrada se enrutó correctamente antes de realizar una operación, suscribirse a y realizar la operación en el <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, o <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> método. Estos métodos se invocan mediante el subproceso de la aplicación una vez realizada la prueba de posicionamiento precisa. Para suscribirse a estos métodos, llame a la <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> método en el método que tiene lugar en el subproceso del lápiz.  
  
 En el diagrama siguiente ilustra la relación entre el subproceso del lápiz y el subproceso de interfaz de usuario con respecto a los eventos de lápiz de un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  
  
 ![Modelos de subprocesamiento de tinta &#40;IU y lápiz&#41;](../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>Representar entrada manuscrita  
 Como el usuario dibuja un trazo, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> representa la tinta en un subproceso independiente de forma que la entrada de lápiz parece "fluir" del lápiz incluso cuando el subproceso de interfaz de usuario está ocupado.  El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> genera un árbol visual en el subproceso de representación dinámica como recopila los puntos del lápiz.  Cuando el usuario finaliza el trazo, el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> le pide que se le notifique cuando la aplicación realiza el siguiente paso de representación.  Cuando la aplicación termina el siguiente paso de representación, el <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> limpia su árbol visual.  El siguiente diagrama ilustra este proceso.  
  
 ![Diagrama de subprocesos de tinta](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1.  El usuario inicia el trazo.  
  
    1.  El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> crea el árbol visual.  
  
2.  El usuario está dibujando el trazo.  
  
    1.  El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> compila el árbol visual.  
  
3.  El usuario finaliza el trazo.  
  
    1.  El <xref:System.Windows.Controls.InkPresenter> agrega el trazo a su árbol visual.  
  
    2.  La capa de integración multimedia (MIL) representa los trazos estáticamente.  
  
    3.  El <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> limpia los objetos visuales.
