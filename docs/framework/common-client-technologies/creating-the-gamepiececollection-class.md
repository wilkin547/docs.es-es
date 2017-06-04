---
title: "Creating the GamePieceCollection Class | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating the GamePieceCollection Class
La clase **GamePieceCollection** deriva de la clase List genérica e incorpora métodos para administrar más fácilmente varios objetos **GamePiece**.  
  
## Crear el código  
 El constructor de la clase **GamePieceCollection** inicializa el miembro privado *capturedIndex*.  Este campo se usa para realizar un seguimiento de las piezas de juego que tienen actualmente la captura del mouse.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 Los métodos **ProcessInertia** y **Draw** simplifican el código necesario en los métodos [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) y [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) del juego; para ello, enumeran todas las piezas de juego en la colección y llaman al método respectivo en cada objeto **GamePiece**.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 También se llama al método **UpdateFromMouse** durante la actualización del juego.  Permite que solo una pieza de juego tenga la captura del mouse y para ello comprueba primero si la captura actual \(si existe\) está aún en vigor.  Si es así, no se permite que ninguna otra pieza obtenga la captura.  
  
 Si ninguna pieza tiene la captura actualmente, el método **UpdateFromMouse** enumera todas las piezas de juego, desde la última a la primera, y comprueba si esa pieza notifica una captura del mouse.  Si es así, esa pieza se convierte en la pieza capturada actual y no se realiza ningún otro procesamiento.  El método **UpdateFromMouse** comprueba primero el último elemento de la colección de manera que dos piezas se superponen, obtendrá la captura la que tenga el orden Z mayor.  El orden Z no es explícito ni modificable; se rige simplemente por el orden con el que se agregan las piezas de juego a la colección.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## Vea también  
 [Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)   
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)