---
title: "Acci&#243;n de finalizaci&#243;n de instancias | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Acci&#243;n de finalizaci&#243;n de instancias
La propiedad **Acción de finalización de instancias** del almacén de instancias de flujo de trabajo de SQL le permite especificar si los datos y metadatos de las instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.Los valores permitidos para esta propiedad son **DeleteAll** y **DeleteNothing**.En la lista siguiente se describen estas opciones:  
  
-   **DeleteAll \(valor predeterminado\).** Si el valor de la propiedad está establecido en DeleteAll, los datos y metadatos de instancias de flujo de trabajo se eliminan de la base de datos de persistencia después de que se hayan completado las instancias.  
  
-   **DeleteNothing.** Si el valor de la propiedad está establecido en DeleteNothing, los datos y metadatos de instancias de flujo de trabajo se mantienen en la base de datos de persistencia incluso después de que se hayan completado las instancias.  
  
    > [!CAUTION]
    >  Mantener la información de estado de la instancia después de que éstas hayan finalizado provoca que el tamaño de la base de datos de persistencia crezca.A medida que esto ocurre, tardan más las operaciones de la base de datos que el subsistema de persistencia realiza, de modo que necesita purgar la información de estado de la instancias de la base de datos de persistencia periódicamente para que los servicios se lleven a cabo con el nivel de satisfacción adecuado para sus necesidades de rendimiento.