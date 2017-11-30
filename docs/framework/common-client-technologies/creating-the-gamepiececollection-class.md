---
title: Crear la clase GamePieceCollection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: b8b53e5890aaebbad2f0a5f0e058182193b11622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="fc34d-102">Crear la clase GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="fc34d-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="fc34d-103">La clase **GamePieceCollection** deriva de la clase List genérica e incorpora métodos para administrar más fácilmente varios objetos **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="fc34d-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="fc34d-104">Crear el código</span><span class="sxs-lookup"><span data-stu-id="fc34d-104">Creating the Code</span></span>  
 <span data-ttu-id="fc34d-105">El constructor de la clase **GamePieceCollection** inicializa el miembro privado *capturedIndex*.</span><span class="sxs-lookup"><span data-stu-id="fc34d-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="fc34d-106">Este campo se usa para realizar un seguimiento de las piezas de juego que tienen actualmente la captura del mouse.</span><span class="sxs-lookup"><span data-stu-id="fc34d-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 <span data-ttu-id="fc34d-107">Los métodos **ProcessInertia** y **Draw** simplifican el código necesario en los métodos [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) y [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) del juego. Para ello, enumeran todas las piezas de juego en la colección y llaman al método respectivo en cada objeto **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="fc34d-107">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 <span data-ttu-id="fc34d-108">También se llama al método **UpdateFromMouse** durante la actualización del juego.</span><span class="sxs-lookup"><span data-stu-id="fc34d-108">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="fc34d-109">Permite que solo una pieza de juego tenga la captura del mouse y para ello comprueba primero si la captura actual (si existe) está aún en vigor.</span><span class="sxs-lookup"><span data-stu-id="fc34d-109">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="fc34d-110">Si es así, no se permite que ninguna otra pieza obtenga la captura.</span><span class="sxs-lookup"><span data-stu-id="fc34d-110">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="fc34d-111">Si ninguna pieza tiene la captura actualmente, el método **UpdateFromMouse** enumera todas las piezas de juego, desde la última a la primera, y comprueba si esa pieza notifica una captura del mouse.</span><span class="sxs-lookup"><span data-stu-id="fc34d-111">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="fc34d-112">Si es así, esa pieza se convierte en la pieza capturada actual y no se realiza ningún otro procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fc34d-112">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="fc34d-113">El método **UpdateFromMouse** comprueba primero el último elemento de la colección de manera que, si dos partes se superponen, obtendrá la captura la que tenga el orden Z mayor.</span><span class="sxs-lookup"><span data-stu-id="fc34d-113">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="fc34d-114">El orden Z no es explícito ni modificable; se rige simplemente por el orden con el que se agregan las piezas de juego a la colección.</span><span class="sxs-lookup"><span data-stu-id="fc34d-114">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a><span data-ttu-id="fc34d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc34d-115">See Also</span></span>  
 [<span data-ttu-id="fc34d-116">Manipulaciones e inercia</span><span class="sxs-lookup"><span data-stu-id="fc34d-116">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="fc34d-117">Usar manipulaciones e inercia en una aplicación XNA</span><span class="sxs-lookup"><span data-stu-id="fc34d-117">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="fc34d-118">Crear la clase GamePiece</span><span class="sxs-lookup"><span data-stu-id="fc34d-118">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="fc34d-119">Crear la clase Game1</span><span class="sxs-lookup"><span data-stu-id="fc34d-119">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [<span data-ttu-id="fc34d-120">Listas de código completas</span><span class="sxs-lookup"><span data-stu-id="fc34d-120">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
