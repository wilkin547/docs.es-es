---
title: Usar manipulaciones e inercia en una aplicación XNA
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 70b8d0c5c098089b6f16ef817ff86698f68cf7c3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248909"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a><span data-ttu-id="f17b8-102">Usar manipulaciones e inercia en una aplicación XNA</span><span class="sxs-lookup"><span data-stu-id="f17b8-102">Using Manipulations and Inertia in an XNA Application</span></span>
<span data-ttu-id="f17b8-103">En este artículo se describe cómo usar manipulaciones y procesamiento de inercia en una aplicación Microsoft XNA para controlar el movimiento de las piezas de juego.</span><span class="sxs-lookup"><span data-stu-id="f17b8-103">This article describes how you can use manipulations and inertia processing in a Microsoft XNA application to control the movement of game pieces.</span></span> <span data-ttu-id="f17b8-104">Antes de leer este artículo, debe estar familiarizado con el tema [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) (Información general sobre manipulaciones e inercia) y estar familiarizado con los conceptos básicos de programación con XNA.</span><span class="sxs-lookup"><span data-stu-id="f17b8-104">Before you read this article, you should be familiar with the [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) topic, and be familiar with basic XNA programming concepts.</span></span>  
  
 <span data-ttu-id="f17b8-105">Para realizar las tareas descritas en este artículo, el proyecto XNA debe hacer referencia al ensamblado <xref:System.Windows.Input.Manipulations> y debe tener [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([descargar](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) instalado en el equipo para que el proyecto pueda hacer referencia a los ensamblados XNA.</span><span class="sxs-lookup"><span data-stu-id="f17b8-105">To perform the tasks described in this article, your XNA project must reference the <xref:System.Windows.Input.Manipulations> assembly, and you must have [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([download](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) installed on your computer so that your project can reference the XNA assemblies.</span></span>  
  
## <a name="overview-of-functionality"></a><span data-ttu-id="f17b8-106">Información general de la funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f17b8-106">Overview of Functionality</span></span>  
 <span data-ttu-id="f17b8-107">En este artículo se muestra cómo crear una clase personalizada que representa una pieza de juego que usa manipulación y procesamiento de inercia.</span><span class="sxs-lookup"><span data-stu-id="f17b8-107">This article shows you how to create a custom class that represents a game piece that uses manipulation and inertia processing.</span></span> <span data-ttu-id="f17b8-108">Esta clase permite manipular una pieza de juego en la pantalla arrastrándola con el mouse y después soltarla.</span><span class="sxs-lookup"><span data-stu-id="f17b8-108">This class enables you to manipulate a game piece across the screen by dragging it with the mouse, and then releasing it.</span></span> <span data-ttu-id="f17b8-109">Una vez soltada, el procesamiento de inercia mantiene la pieza de juego en movimiento mientras se ralentiza gradualmente.</span><span class="sxs-lookup"><span data-stu-id="f17b8-109">Once released, inertia processing keeps the game piece moving as it gradually slows down.</span></span> <span data-ttu-id="f17b8-110">El movimiento es lineal y angular.</span><span class="sxs-lookup"><span data-stu-id="f17b8-110">Movement is both linear and angular.</span></span>  
  
 <span data-ttu-id="f17b8-111">![Aplicación sencilla de manipulaciones e inercia.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span><span class="sxs-lookup"><span data-stu-id="f17b8-111">![A simple manipulations and inertia application.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span></span>  
  
 <span data-ttu-id="f17b8-112">Además, se crea una colección personalizada que administra varias piezas de juego.</span><span class="sxs-lookup"><span data-stu-id="f17b8-112">In addition, a custom collection is created that manages multiple game pieces.</span></span> <span data-ttu-id="f17b8-113">Esto simplifica el control que se requiere de la clase XNA Game.</span><span class="sxs-lookup"><span data-stu-id="f17b8-113">This simplifies the handling that is required from the XNA Game class.</span></span>  
  
 [<span data-ttu-id="f17b8-114">Crear la clase GamePiece</span><span class="sxs-lookup"><span data-stu-id="f17b8-114">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [<span data-ttu-id="f17b8-115">Crear la clase GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="f17b8-115">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [<span data-ttu-id="f17b8-116">Crear la clase Game1</span><span class="sxs-lookup"><span data-stu-id="f17b8-116">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [<span data-ttu-id="f17b8-117">Listas de código completas</span><span class="sxs-lookup"><span data-stu-id="f17b8-117">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a><span data-ttu-id="f17b8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f17b8-118">See Also</span></span>  
 <xref:System.Windows.Input.Manipulations>  
 [<span data-ttu-id="f17b8-119">Información general sobre manipulaciones e inercia</span><span class="sxs-lookup"><span data-stu-id="f17b8-119">Manipulations and Inertia Overview</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
