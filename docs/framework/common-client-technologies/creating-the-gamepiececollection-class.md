---
title: Crear la clase GamePieceCollection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b74702d71113c3a9dac654971e7d02f97016218b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="d4c44-102">Crear la clase GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="d4c44-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="d4c44-103">La clase **GamePieceCollection** deriva de la clase List genérica e incorpora métodos para administrar más fácilmente varios objetos **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="d4c44-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="d4c44-104">Crear el código</span><span class="sxs-lookup"><span data-stu-id="d4c44-104">Creating the Code</span></span>  
 <span data-ttu-id="d4c44-105">El constructor de la clase **GamePieceCollection** inicializa el miembro privado *capturedIndex*.</span><span class="sxs-lookup"><span data-stu-id="d4c44-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="d4c44-106">Este campo se usa para realizar un seguimiento de las piezas de juego que tienen actualmente la captura del mouse.</span><span class="sxs-lookup"><span data-stu-id="d4c44-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 <span data-ttu-id="d4c44-107">[!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]</span><span class="sxs-lookup"><span data-stu-id="d4c44-107">[!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]</span></span>  
  
 <span data-ttu-id="d4c44-108">Los métodos **ProcessInertia** y **Draw** simplifican el código necesario en los métodos [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) y [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) del juego. Para ello, enumeran todas las piezas de juego en la colección y llaman al método respectivo en cada objeto **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="d4c44-108">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 <span data-ttu-id="d4c44-109">[!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]</span><span class="sxs-lookup"><span data-stu-id="d4c44-109">[!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]</span></span>  
  
 <span data-ttu-id="d4c44-110">También se llama al método **UpdateFromMouse** durante la actualización del juego.</span><span class="sxs-lookup"><span data-stu-id="d4c44-110">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="d4c44-111">Permite que solo una pieza de juego tenga la captura del mouse y para ello comprueba primero si la captura actual (si existe) está aún en vigor.</span><span class="sxs-lookup"><span data-stu-id="d4c44-111">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="d4c44-112">Si es así, no se permite que ninguna otra pieza obtenga la captura.</span><span class="sxs-lookup"><span data-stu-id="d4c44-112">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="d4c44-113">Si ninguna pieza tiene la captura actualmente, el método **UpdateFromMouse** enumera todas las piezas de juego, desde la última a la primera, y comprueba si esa pieza notifica una captura del mouse.</span><span class="sxs-lookup"><span data-stu-id="d4c44-113">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="d4c44-114">Si es así, esa pieza se convierte en la pieza capturada actual y no se realiza ningún otro procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d4c44-114">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="d4c44-115">El método **UpdateFromMouse** comprueba primero el último elemento de la colección de manera que, si dos partes se superponen, obtendrá la captura la que tenga el orden Z mayor.</span><span class="sxs-lookup"><span data-stu-id="d4c44-115">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="d4c44-116">El orden Z no es explícito ni modificable; se rige simplemente por el orden con el que se agregan las piezas de juego a la colección.</span><span class="sxs-lookup"><span data-stu-id="d4c44-116">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 <span data-ttu-id="d4c44-117">[!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]</span><span class="sxs-lookup"><span data-stu-id="d4c44-117">[!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c44-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4c44-118">See Also</span></span>  
 <span data-ttu-id="d4c44-119">[Manipulaciones e inercia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md) </span><span class="sxs-lookup"><span data-stu-id="d4c44-119">[Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md) </span></span>  
 <span data-ttu-id="d4c44-120">[Usar manipulaciones e inercia en una aplicación XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md) </span><span class="sxs-lookup"><span data-stu-id="d4c44-120">[Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md) </span></span>  
 <span data-ttu-id="d4c44-121">[Crear la clase GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md) </span><span class="sxs-lookup"><span data-stu-id="d4c44-121">[Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md) </span></span>  
 <span data-ttu-id="d4c44-122">[Crear la clase Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md) </span><span class="sxs-lookup"><span data-stu-id="d4c44-122">[Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md) </span></span>  
 [<span data-ttu-id="d4c44-123">Listas de código completas</span><span class="sxs-lookup"><span data-stu-id="d4c44-123">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)

