---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: aaf89f73b6de250aaa572b8fef31e5a1ebd5482b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcommonbehaviorsgt"></a>&lt;commonBehaviors&gt;
La sección `commonBehaviors` sólo se puede definir en el archivo machine.config. Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y servicios del equipo. Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios. Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.
