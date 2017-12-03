---
title: "Opción de codificación de instancias"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a874f88b787a99af0461ff47c3ae246442af2f19
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="instance-encoding-option"></a>Opción de codificación de instancias
El **opción de codificación de la instancia** propiedad del almacén de instancia de flujo de trabajo de SQL le permite especificar si el proveedor de persistencia de SQL debe comprimir la información de estado de instancia de flujo de trabajo utilizando el algoritmo GZip antes de guardar el información en la base de datos de persistencia. Los valores permitidos para esta propiedad son: GZip y Ninguno. El valor predeterminado es None. En la lista siguiente se describen estas opciones.  
  
1.  **GZip**. El proveedor de persistencia codifica la información de estado mediante el algoritmo del GZip antes de conservar la información de estado en la base de datos de persistencia.  
  
2.  **Ninguno**. El proveedor de persistencia no codifica la información de estado antes de guardar la información en la base de datos de persistencia.  
  
 Codificar la información de estado de la instancia de flujo de trabajo mediante GZip reduce el consumo de memoria en SQL Database y también el del consumo de la red si la base de datos reside en un equipo diferente en la red del equipo en el que el host de servicio de flujo de trabajo se está ejecutando. Un Consejo general es definir la **opción de codificación de la instancia** propiedad **ninguno** si el estado de la instancia de flujo de trabajo es pequeño.
