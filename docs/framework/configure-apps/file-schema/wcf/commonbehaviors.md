---
title: "&lt;commonBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;commonBehaviors&gt;
La sección `commonBehaviors` sólo se puede definir en el archivo machine.config.  Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y servicios del equipo.  Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios.  Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.