---
title: "Acción de finalización de instancias"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3fa2eb347bc69a89545e6145154306f012e23490
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="instance-completion-action"></a>Acción de finalización de instancias
El **acción de finalización de la instancia** propiedad del almacén de instancia de flujo de trabajo de SQL le permite especificar si los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias. Los valores permitidos para esta propiedad son **DeleteAll** y **DeleteNothing**. En la lista siguiente se describen estas opciones:  
  
-   **DeleteAll (valor predeterminado).** Si el valor de la propiedad está establecido en DeleteAll, los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.  
  
-   **DeleteNothing.** Si el valor de la propiedad está establecido en DeleteNothing, los datos y metadatos de instancias de flujo de trabajo se mantienen en la base de datos de persistencia incluso después de que se hayan completado las instancias.  
  
    > [!CAUTION]
    >  Mantener la información de estado de la instancia después de que éstas hayan finalizado provoca que el tamaño de la base de datos de persistencia crezca. A medida que esto ocurre, tardan más las operaciones de la base de datos que el subsistema de persistencia realiza, de modo que necesita purgar la información de estado de la instancias de la base de datos de persistencia periódicamente para que los servicios se lleven a cabo con el nivel de satisfacción adecuado para sus necesidades de rendimiento.
