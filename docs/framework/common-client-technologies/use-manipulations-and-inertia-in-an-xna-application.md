---
title: Usar manipulaciones e inercia en una aplicación XNA
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 78deee127f43aac71a1a4daaab808598065c2fe5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741677"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>Usar manipulaciones e inercia en una aplicación XNA
En este artículo se describe cómo usar manipulaciones y procesamiento de inercia en una aplicación Microsoft XNA para controlar el movimiento de las piezas de juego. Antes de leer este artículo, debe estar familiarizado con el tema [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) (Información general sobre manipulaciones e inercia) y estar familiarizado con los conceptos básicos de programación con XNA.  
  
 Para realizar las tareas descritas en este artículo, el proyecto XNA debe hacer referencia al ensamblado <xref:System.Windows.Input.Manipulations> y debe tener [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([descargar](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) instalado en el equipo para que el proyecto pueda hacer referencia a los ensamblados XNA.  
  
## <a name="overview-of-functionality"></a>Información general de la funcionalidad  
 En este artículo se muestra cómo crear una clase personalizada que representa una pieza de juego que usa manipulación y procesamiento de inercia. Esta clase permite manipular una pieza de juego en la pantalla arrastrándola con el mouse y después soltarla. Una vez soltada, el procesamiento de inercia mantiene la pieza de juego en movimiento mientras se ralentiza gradualmente. El movimiento es lineal y angular.  
  
 ![Aplicación sencilla de manipulaciones e inercia.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")  
  
 Además, se crea una colección personalizada que administra varias piezas de juego. Esto simplifica el control que se requiere de la clase XNA Game.  
  
 [Crear la clase GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Crear la clase GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Crear la clase Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Listas de código completas](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Input.Manipulations>  
 [Información general sobre manipulaciones e inercia](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
