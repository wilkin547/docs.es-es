---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ltcommonbehaviorsgt"></a>&lt;commonBehaviors&gt;
La sección `commonBehaviors` sólo se puede definir en el archivo machine.config. Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos WCF y servicios en el equipo. Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios. Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.
