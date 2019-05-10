---
title: Acción de finalización de instancias
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: d68f41a586e44f96c9ca26cf8a142a2782adaa36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662976"
---
# <a name="instance-completion-action"></a>Acción de finalización de instancias
El **acción de finalización de la instancia** propiedad del Store de instancia de flujo de trabajo de SQL le permite especificar si los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias. Los valores permitidos para esta propiedad son **DeleteAll** y **DeleteNothing**. En la lista siguiente se describen estas opciones:  
  
- **DeleteAll (valor predeterminado).** Si el valor de la propiedad está establecido en DeleteAll, los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.  
  
- **DeleteNothing.** Si el valor de la propiedad está establecido en DeleteNothing, los datos y metadatos de instancias de flujo de trabajo se mantienen en la base de datos de persistencia incluso después de que se hayan completado las instancias.  
  
    > [!CAUTION]
    >  Mantener la información de estado de la instancia después de que éstas hayan finalizado provoca que el tamaño de la base de datos de persistencia crezca. A medida que esto ocurre, tardan más las operaciones de la base de datos que el subsistema de persistencia realiza, de modo que necesita purgar la información de estado de la instancias de la base de datos de persistencia periódicamente para que los servicios se lleven a cabo con el nivel de satisfacción adecuado para sus necesidades de rendimiento.
