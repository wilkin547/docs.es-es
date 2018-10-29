---
title: Crear la clase Game1
ms.date: 03/30/2017
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
ms.openlocfilehash: c96fa846d11947af03faec26dd6de99e0aeec052
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452802"
---
# <a name="creating-the-game1-class"></a>Crear la clase Game1
Igual que con todos los proyectos de Microsoft XNA, la clase Game1 deriva de la clase [Microsoft.Xna.Framework.Game](https://docs.microsoft.com/previous-versions/windows/xna/bb197040%28v%3dxnagamestudio.41%29), que proporciona funciones básicas de inicialización de dispositivos de gráficos, lógica de juego y código de representación para juegos de XNA. La clase Game1 es bastante simple porque la mayor parte del trabajo se realiza en las clases GamePiece y GamePieceCollection.  
  
## <a name="creating-the-code"></a>Crear el código  
 Los miembros privados de la clase se componen de un objeto **GamePieceCollection** para contener las piezas de juego, un objeto [GraphicsDeviceManager](https://docs.microsoft.com/previous-versions/windows/xna/bb197317%28v%3dxnagamestudio.41%29) y un objeto [SpriteBatch](https://docs.microsoft.com/previous-versions/windows/xna/bb199034%28v%3dxnagamestudio.41%29) que se usa para representar las piezas de juego.  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 Durante la inicialización del juego se crean instancias de estos objetos.  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 Cuando se llama al método [LoadContent](https://docs.microsoft.com/previous-versions/windows/xna/bb975766%28v%3dxnagamestudio.41%29), se crean las piezas de juego y se asignan al objeto **GamePieceCollection**. Hay dos tipos de piezas de juego. El factor de escala de las piezas cambia ligeramente para que haya piezas algo más pequeñas y algo más grandes.  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 XNA Framework llama al método [Update](https://docs.microsoft.com/previous-versions/windows/xna/bb199616%28v%3dxnagamestudio.41%29) repetidamente mientras el juego se está ejecutando. El método [Update](https://docs.microsoft.com/previous-versions/windows/xna/bb199616%28v%3dxnagamestudio.41%29) llama a los métodos **ProcessInertia** y **UpdateFromMouse** en la colección de piezas de juego. Estos métodos se describen en [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) (Crear la clase GamePieceCollection).  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 XNA Framework llama también al método [Draw](https://docs.microsoft.com/previous-versions/windows/xna/bb196422%28v%3dxnagamestudio.41%29) repetidamente mientras el juego se está ejecutando. El método [Draw](https://docs.microsoft.com/previous-versions/windows/xna/bb196422%28v%3dxnagamestudio.41%29) llama al método **Draw** del objeto **GamePieceCollection** para realizar la representación de las piezas de juego. Este método se describe en [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) (Crear la clase GamePieceCollection).  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a>Vea también  
 [Manipulaciones e inercia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Usar manipulaciones e inercia en una aplicación XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Crear la clase GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Crear la clase GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [Listas de código completas](../../../docs/framework/common-client-technologies/full-code-listings.md)
