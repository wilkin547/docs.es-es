---
title: Crear la clase Game1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7453c4f650e2dcadd3b8fac27b66f4db97fa0136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-game1-class"></a>Crear la clase Game1
Igual que con todos los proyectos de Microsoft XNA, la clase Game1 deriva de la clase [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx), que proporciona funciones básicas de inicialización de dispositivos de gráficos, lógica de juego y código de representación para juegos de XNA. La clase Game1 es bastante simple porque la mayor parte del trabajo se realiza en las clases GamePiece y GamePieceCollection.  
  
## <a name="creating-the-code"></a>Crear el código  
 Los miembros privados de la clase se componen de un objeto **GamePieceCollection** para contener las piezas de juego, un objeto [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) y un objeto [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) que se usa para representar las piezas de juego.  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 Durante la inicialización del juego se crean instancias de estos objetos.  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 Cuando se llama al método [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx), se crean las piezas de juego y se asignan al objeto **GamePieceCollection**. Hay dos tipos de piezas de juego. El factor de escala de las piezas cambia ligeramente para que haya piezas algo más pequeñas y algo más grandes.  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 XNA Framework llama al método [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) repetidamente mientras el juego se está ejecutando. El método [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) llama a los métodos **ProcessInertia** y **UpdateFromMouse** en la colección de piezas de juego. Estos métodos se describen en [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) (Crear la clase GamePieceCollection).  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 XNA Framework llama también al método [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) repetidamente mientras el juego se está ejecutando. El método [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) llama al método **Draw** del objeto **GamePieceCollection** para realizar la representación de las piezas de juego. Este método se describe en [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) (Crear la clase GamePieceCollection).  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a>Vea también  
 [Manipulaciones e inercia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Usar manipulaciones e inercia en una aplicación XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Crear la clase GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Crear la clase GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [Listas de código completas](../../../docs/framework/common-client-technologies/full-code-listings.md)
