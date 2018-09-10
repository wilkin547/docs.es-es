---
title: Crear la clase GamePieceCollection
ms.date: 03/30/2017
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
ms.openlocfilehash: 6323122735273f77bfe9d61bf2df84cabe3e5d6c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041231"
---
# <a name="creating-the-gamepiececollection-class"></a>Crear la clase GamePieceCollection
La clase **GamePieceCollection** deriva de la clase List genérica e incorpora métodos para administrar más fácilmente varios objetos **GamePiece**.  
  
## <a name="creating-the-code"></a>Crear el código  
 El constructor de la clase **GamePieceCollection** inicializa el miembro privado *capturedIndex*. Este campo se usa para realizar un seguimiento de las piezas de juego que tienen actualmente la captura del mouse.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 Los métodos **ProcessInertia** y **Draw** simplifican el código necesario en los métodos [Game.Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) y [Game.Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) del juego. Para ello, enumeran todas las piezas de juego en la colección y llaman al método respectivo en cada objeto **GamePiece**.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 También se llama al método **UpdateFromMouse** durante la actualización del juego. Permite que solo una pieza de juego tenga la captura del mouse y para ello comprueba primero si la captura actual (si existe) está aún en vigor. Si es así, no se permite que ninguna otra pieza obtenga la captura.  
  
 Si ninguna pieza tiene la captura actualmente, el método **UpdateFromMouse** enumera todas las piezas de juego, desde la última a la primera, y comprueba si esa pieza notifica una captura del mouse. Si es así, esa pieza se convierte en la pieza capturada actual y no se realiza ningún otro procesamiento. El método **UpdateFromMouse** comprueba primero el último elemento de la colección de manera que, si dos partes se superponen, obtendrá la captura la que tenga el orden Z mayor. El orden Z no es explícito ni modificable; se rige simplemente por el orden con el que se agregan las piezas de juego a la colección.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a>Vea también  
 [Manipulaciones e inercia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Usar manipulaciones e inercia en una aplicación XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Crear la clase GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Crear la clase Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [Listas de código completas](../../../docs/framework/common-client-technologies/full-code-listings.md)
