---
title: "Opci&#243;n de codificaci&#243;n de instancias | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Opci&#243;n de codificaci&#243;n de instancias
La propiedad **Opción de codificación de instancias** del almacén de instancias de flujo de trabajo de SQL le permite especificar si el proveedor de persistencia de SQL debe comprimir la información sobre el estado de la instancia de flujo de trabajo mediante el algoritmo del GZip antes de guardar la información en la base de datos de persistencia.Los valores permitidos para esta propiedad son: GZip y Ninguno.El valor predeterminado es None.En la lista siguiente se describen estas opciones.  
  
1.  **GZip**.El proveedor de persistencia codifica la información de estado mediante el algoritmo del GZip antes de conservar la información de estado en la base de datos de persistencia.  
  
2.  **Ninguno**.El proveedor de persistencia no codifica la información de estado antes de guardar la información en la base de datos de persistencia.  
  
 Codificar la información de estado de la instancia de flujo de trabajo mediante GZip reduce el consumo de memoria en la base de datos SQL y también el del consumo de la red si la base de datos reside en un equipo diferente en la red del equipo en el que el host de servicio de flujo de trabajo se está ejecutando.Un consejo general es definir la propiedad **Opción de codificación de instancias** en **Ninguno** si el estado de la instancia de flujo de trabajo es pequeño.