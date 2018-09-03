---
title: Información general sobre manipulaciones e inercia
ms.date: 03/30/2017
ms.assetid: dd31b89b-eab6-45a1-8d0b-11e0eb84b234
ms.openlocfilehash: 41c22dc305f8ef653705436544ab2342e55ed02a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401230"
---
# <a name="manipulations-and-inertia-overview"></a>Información general sobre manipulaciones e inercia
Las *manipulaciones* permiten a los usuarios mover, girar y cambiar de tamaño los elementos de la interfaz de usuario (UI) con *manipuladores*. Un manipulador representa un mouse o (en los escenarios táctiles) un lápiz o un dedo.  
  
 La *inercia* emula el comportamiento real de los elementos de la UI que están en movimiento, ya que simula fuerzas de fricción en los elementos. Esto permite que el movimiento (lineal y angular) de los elementos se ralentice gradualmente antes de detenerse. Este artículo proporciona una introducción a las manipulaciones y la inercia en .NET Framework.  
  
## <a name="manipulations"></a>Manipulaciones  
 Cada manipulación trata una colección de manipuladores como un objeto compuesto. La aplicación puede realizar el seguimiento de los cambios en el objeto compuesto en lugar de los componentes individuales.  
  
 Observe la imagen de la siguiente ilustración. El usuario puede utilizar dos manipuladores para mover, girar y escalar la imagen. Los cambios realizados en cada manipulador se interpretan junto con los demás manipuladores.  
  
 Por ejemplo, si tiene dos manipuladores (1 y 2) en la imagen y mueve el manipulador 1 en dirección +Y (hacia abajo), el cambio que se realice en la imagen dependerá de lo que le ocurra al manipulador 2. Si el manipulador 2 también se mueve en dirección +Y (hacia abajo), la imagen se moverá, simplemente, en la dirección +Y. Pero si el manipulador 2 no cambia, o si se mueve en dirección -Y (hacia arriba), la imagen se reducirá o se girará.  
  
 ![Fotografía virtual que manipulan dos dedos.](../../../docs/framework/common-client-technologies/media/manipulation-resize.png "Manipulation_Resize")  
  
 Imagen manipulada por dos manipuladores  
  
 El procesamiento de la manipulación proporciona un marco que supervisa un subconjunto de manipuladores y los interpreta como si actuaran conjuntamente, en lugar de por separado. Puede crear varios objetos del procesador de manipulación de forma simultánea, uno por cada elemento de la UI que vaya a manipularse en una aplicación. Al procesador de manipulación se le informa de qué dispositivos de entrada debe observar y este informa de las manipulaciones a través de [eventos de .NET](https://msdn.microsoft.com/library/17sde2xt.aspx).  
  
 El procesador de manipulación no tiene información sobre el elemento concreto que se está manipulando. La aplicación, por su cuenta, aplica los cambios a un elemento específico de la aplicación. Por ejemplo, una aplicación aplica transformaciones a una imagen o vuelve a dibujarla para mostrarla en su nueva ubicación o con otro tamaño u otra orientación.  
  
 Las manipulaciones están diseñadas para [transformaciones afines](/windows/desktop/gdiplus/-gdiplus-transformations-use) bidimensionales (2D). Estas transformaciones incluyen trasladar, girar y escalar.  
  
### <a name="parts-of-a-manipulation"></a>Partes de una manipulación  
 Una manipulación es una colección de objetos <xref:System.Windows.Input.Manipulations.Manipulator2D>. La manipulación agregada se representa con un punto de origen y una elipse. El punto de origen es la posición media de todos los manipuladores que están manipulando un elemento. La elipse tiene un radio que es la distancia media entre el origen y cada uno de los objetos <xref:System.Windows.Input.Manipulations.Manipulator2D>.  
  
 ![Partes de una manipulación.](../../../docs/framework/common-client-technologies/media/manipulation-definition.png "Manipulation_Definition")  
  
 Dos manipuladores (1 y 2), un origen y una elipse especifican una manipulación  
  
 A medida que se agregan, se mueven o se quitan manipuladores de un elemento de la UI, la aplicación actualiza el objeto <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> llamando al método <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.ProcessManipulators%2A>. Cuando se inicia la manipulación por primera vez, se genera el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Started>.  
  
> [!NOTE]
>  El procesamiento de la manipulación es más eficiente cuando se utiliza en un entorno de actualización basado en el marco. Si se usa el procesamiento de la manipulación en una aplicación de Microsoft XNA, esto no es un problema, dado que el marco XNA proporciona actualizaciones basadas en el marco con el método [Game.Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx). En otros entornos (como WinForms), puede que tenga que proporcionar su propia lógica basada en el marco para recopilar las manipulaciones y enviarlas periódicamente al método <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.ProcessManipulators%2A> en forma de lote.  
  
 A medida que cambian el número de manipuladores o su posición, se genera el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta>. Las propiedades del objeto <xref:System.Windows.Input.Manipulations.Manipulation2DDeltaEventArgs> que se pasa al controlador de eventos <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta> especifican los cambios en el origen, la escala, la rotación y la traslación que se produjeron desde el último evento. El origen de la manipulación cambia cuando se mueven los manipuladores y cuando se agregan o se quitan manipuladores. Los valores de traslación especifican cuánto movimiento de X o Y incluye la manipulación.  
  
 Con los nuevos valores, la aplicación dibuja de nuevo el elemento de la UI.  
  
 ![Manipulación después de que el contacto A se haya desplazado a la derecha.](../../../docs/framework/common-client-technologies/media/manipulation-changed.png "Manipulation_Changed")  
  
 El manipulador 1 se mueve y hace que el origen cambie  
  
 Cuando se quita del objeto <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> el último manipulador que está asociado a la manipulación, se genera el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed>.  
  
### <a name="the-manipulation-processing-model"></a>El modelo de procesamiento de la manipulación  
 Los procesadores de manipulación utilizan un modelo de uso directo. Con este sencillo modelo, la aplicación debe pasar los detalles del evento de entrada al procesador de manipulación. Cualquier primitivo de entrada, como un dispositivo de mouse, un lápiz o un dedo, puede generar un evento de entrada. Este proceso proporciona un mecanismo de filtrado directo y un modelo de uso sencillo, para que la aplicación pueda procesar por lotes los eventos de entrada cuando sea necesario.  
  
 La aplicación, para incluir un primitivo de entrada en el proceso de manipulación, crea una estructura de <xref:System.Windows.Input.Manipulations.Manipulator2D> a partir de los detalles del primitivo de entrada y pasa la estructura al procesador de manipulación con el método <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.ProcessManipulators%2A>. Entonces, el procesador de manipulación genera eventos que la aplicación debe administrar para actualizar el componente visual de la manera adecuada.  
  
 ![Flujo del modelo de uso directo de manipulaciones.](../../../docs/framework/common-client-technologies/media/manipulation-flow.png "Manipulation_Flow")  
  
 El modelo de procesamiento de la manipulación  
  
## <a name="inertia"></a>Inercia  
 El procesador de inercia permite a las aplicaciones extrapolar la ubicación, la orientación y otras propiedades de un elemento de la UI simulando el comportamiento real.  
  
 Por ejemplo, cuando un usuario se desplaza por un elemento, puede continuar el movimiento, reducir la velocidad y, luego, detenerlo lentamente. El procesador de inercia implementa este comportamiento haciendo que los valores de 2D afines (origen, escala, traslación y rotación) cambien durante un tiempo especificado a una velocidad de desaceleración especificada.  
  
 Como con el procesamiento de la manipulación, el procesador de inercia no tiene información sobre ningún elemento determinado de la UI. En respuesta a los eventos que se generan en un objeto <xref:System.Windows.Input.Manipulations.InertiaProcessor2D>, la aplicación aplica los cambios por separado a un elemento específico de la aplicación.  
  
 El procesamiento de la inercia y el de la manipulación suelen utilizarse conjuntamente. Sus interfaces son similares y los eventos que generan son (en algunos casos) idénticos. Por lo general, el procesamiento de la inercia comienza cuando se completa la manipulación del elemento de la UI, escuchando al evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed> e iniciando el procesamiento de la inercia a partir de ese controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Input.Manipulations>
