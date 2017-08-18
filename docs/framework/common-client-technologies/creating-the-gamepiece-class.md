---
title: Crear la clase GamePiece
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a27a86-ac1c-47be-b477-cb4b819459d3
caps.latest.revision: 9
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7ac9884766812cd635b5a70c028cf15c19838511
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="creating-the-gamepiece-class"></a>Crear la clase GamePiece
La clase **GamePiece** encapsula toda la funcionalidad necesaria para cargar una imagen de pieza de juego de Microsoft XNA, realizar un seguimiento del estado del mouse en relación con la pieza de juego, capturar el mouse, proporcionar el procesamiento de la manipulación y la inercia y proporcionar la capacidad de rebotar cuando la pieza de juego llega a los límites del área de vista.  
  
## <a name="private-members"></a>Miembros privados  
 En la parte superior de la clase **GamePiece**, se declaran varios miembros privados.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privatemembers)]  
  
## <a name="public-properties"></a>Propiedades públicas  
 Tres de estos miembros privados se exponen a través de propiedades públicas. Las propiedades **Scale** y **PieceColor** permiten a la aplicación especificar la escala y el color de la pieza, respectivamente. La propiedad **Bounds** se expone para que una pieza pueda usar los límites de otra al representarse a sí misma: por ejemplo, cuando una pieza debe superponerse a otra. El código siguiente muestra la declaración de las propiedades públicas.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PublicProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_publicproperties)]  
  
## <a name="class-constructor"></a>Constructor de clase  
 El constructor de la clase **GamePiece** acepta los siguientes parámetros:  
  
-   Un tipo [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx). La referencia que se pasa aquí se asigna al miembro privado `spriteBatch`, y se usa para obtener acceso al método [SpriteBatch.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.draw.aspx) cuando la pieza de juego se representa a sí misma. Además, se usa la propiedad [GraphicsDevice](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.graphicsdevice.aspx) para crear el objeto [Texture](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.texture.aspx) asociado a la pieza de juego y para obtener el tamaño del área de vista, a fin de detectar cuándo llega la pieza de juego al límite de una ventana, de modo que pueda rebotar.  
  
-   Una cadena que especifica el nombre de archivo de la imagen que se utilizará para la pieza de juego.  
  
 El constructor también crea un objeto <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> y un objeto <xref:System.Windows.Input.Manipulations.InertiaProcessor2D>, y establece controladores de eventos para sus eventos.  
  
 En el código siguiente se muestra el constructor de la clase **GamePiece**.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Constructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_constructor)]  
  
## <a name="capturing-mouse-input"></a>Captura de la entrada del mouse  
 El método **UpdateFromMouse** es el responsable de detectar cuándo se presiona un botón del mouse mientras el mouse está dentro de los límites de la pieza de juego, y de detectar cuándo se libera el botón del mouse.  
  
 Cuando se presiona el botón primario del mouse (mientras el mouse está dentro de los límites de la pieza), este método establece una marca para indicar que esta pieza de juego capturó el mouse, y comienza el procesamiento de la manipulación.  
  
 El procesamiento de la manipulación se inicia creando una matriz de objetos <xref:System.Windows.Input.Manipulations.Manipulator2D> y pasándolos al objeto <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D>. Esto hace que el procesador de manipulación evalúe los manipuladores (en este caso, un solo manipulador) y genere eventos de manipulación.  
  
 Además, se guarda el punto en el que se está produciendo la operación de arrastre. Este punto se utilizará posteriormente durante el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta> para ajustar los valores de traslación delta, de modo que la pieza de juego se alinee detrás del punto de arrastre.  
  
 Por último, este método devuelve el estado de la captura del mouse. Esto permite al objeto [GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) administrar las capturas cuando hay varias piezas de juego.  
  
 En el código siguiente se muestra el método **UpdateFromMouse**.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_updatefrommouse)]  
  
## <a name="processing-manipulations"></a>Procesamiento de las manipulaciones  
 Cuando se inicia la manipulación, se genera el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Started>. El controlador de este evento detiene el procesamiento de la inercia si se está produciendo y establece la marca *processInertia* en `false`.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationStarted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationstarted)]  
  
 A medida que cambian los valores asociados a la manipulación, se genera el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta>. El controlador de este evento utiliza los valores de delta pasados en los argumentos del evento para realizar cambios en los valores de posición y rotación de la pieza de juego.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationdelta)]  
  
 Cuando se quitan todos los manipuladores (en este caso, un solo manipulador) asociados a una manipulación, el procesador de manipulación genera el evento <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed>. El controlador de este evento comienza el procesamiento de la inercia estableciendo las velocidades iniciales del procesador de inercia de acuerdo con lo indicado por los argumentos del evento, y establece la marca *processInertia* en `true`.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationcompleted)]  
  
## <a name="processing-inertia"></a>Procesamiento de la inercia  
 A medida que el procesamiento de la inercia extrapola nuevos valores para las velocidades lineal y angular, las coordenadas de posición (traslación) y la rotación, se genera el evento <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>. El controlador de este evento utiliza los valores de delta pasados en los argumentos del evento para modificar la posición y la rotación de la pieza de juego.  
  
 Si las nuevas coordenadas hacen que la pieza de juego se mueva más allá de los límites del área de vista, se invertirá la velocidad del procesamiento de la inercia. Esto hace que la pieza de juego rebote y se aleje del límite del área de vista que alcanzó.  
  
 No puede cambiar las propiedades de un objeto <xref:System.Windows.Input.Manipulations.InertiaProcessor2D> mientras el objeto está ejecutando la extrapolación. Por esto, cuando se invierte la velocidad X o Y, el controlador del evento detiene primero la inercia llamando al método <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Complete%2A>. Luego, asigna los nuevos valores de velocidad inicial de acuerdo con los valores de velocidad actuales (ajustados para el comportamiento de esponja), y establece la marca *processInertia* como `true`.  
  
 El código siguiente muestra el controlador de eventos correspondiente al evento <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiadelta)]  
  
 Cuando se completa el procesamiento de la inercia, el procesador de inercia genera el evento <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Completed>. El controlador de este evento establece la marca *processInertia* en `false`.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiacompleted)]  
  
 Ninguna parte de la lógica presentada hasta ahora hace que se produzca la extrapolación de la inercia en sí. Esto se realiza en el método **ProcessInertia**. Este método, al que se llama repetidamente desde el bucle de actualización del juego (el método [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)) comprueba si la marca *processInertia* está establecida en `true` y, si es así, llama al método <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Process%2A>. Llamar a este método provoca la extrapolación y genera el evento <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_ProcessInertia](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_processinertia)]  
  
 La pieza de juego no se representa realmente hasta que se llama a una de las sobrecargas del método Draw. Se llama repetidamente a la primera sobrecarga de este método desde el bucle de dibujo del juego (el método [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)). Esto hace que la pieza de juego se represente con los factores actuales de posición, rotación y escala.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Draw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_draw)]  
  
## <a name="additional-properties"></a>Propiedades adicionales  
 La clase **GamePiece** usa tres propiedades privadas.  
  
1.  **Timestamp**: obtiene un valor de marca de tiempo que usarán los procesadores de manipulación y de inercia.  
  
2.  **X**: obtiene o establece la coordenada X de la pieza de juego. Cuando se establece, ajusta los límites que se usan para la prueba de acierto y la ubicación de los pivotes del procesador de manipulación.  
  
3.  **Y**: obtiene o establece la coordenada Y de la pieza de juego. Cuando se establece, ajusta los límites que se usan para la prueba de acierto y la ubicación de los pivotes del procesador de manipulación.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privateproperties)]  
  
## <a name="see-also"></a>Vea también  
 [Manipulaciones e inercia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Usar manipulaciones e inercia en una aplicación XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Crear la clase GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)   
 [Crear la clase Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)

