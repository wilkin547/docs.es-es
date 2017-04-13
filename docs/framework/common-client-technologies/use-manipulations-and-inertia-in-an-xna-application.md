---
title: "Using Manipulations and Inertia in an XNA Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Using Manipulations and Inertia in an XNA Application
En este artículo se describe cómo usar manipulaciones y procesamiento de inercia en una aplicación Microsoft XNA para controlar el movimiento de las piezas de juego.  Antes de leer este artículo, debe estar familiarizado con el tema [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) y estar familiarizado con los conceptos básicos de programación con XNA.  
  
 Para realizar las tareas descritas en este artículo, su proyecto XNA debe hacer referencia al ensamblado <xref:System.Windows.Input.Manipulations> y debe tener [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) \([descargar](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)\) instalado en el equipo para que el proyecto pueda hacer referencia a los ensamblados XNA.  
  
## Información general de la funcionalidad  
 En este artículo se muestra cómo crear una clase personalizada que representa una pieza de juego que usa manipulación y procesamiento de inercia.  Esta clase permite manipular una pieza de juego en la pantalla arrastrándola con el mouse y después soltarla.  Una vez soltada, el procesamiento de inercia mantiene la pieza de juego en movimiento mientras se ralentiza gradualmente.  El movimiento es lineal y angular.  
  
 ![Una aplicación sencilla de manipulaciones e inercia.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.png "NDP\_GameXna")  
  
 Además, se crea una colección personalizada que administra varias piezas de juego.  Esto simplifica el control que se requiere de la clase XNA Game.  
  
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## Vea también  
 <xref:System.Windows.Input.Manipulations>   
 [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)