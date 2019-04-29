---
title: Opción de codificación de instancias
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: c4de7c45d899f45a7b5b71d563257d9accb8fdbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928727"
---
# <a name="instance-encoding-option"></a>Opción de codificación de instancias
El **opción de codificación de la instancia** propiedad del Store de instancia de flujo de trabajo de SQL le permite especificar si el proveedor de persistencia de SQL debe comprimir la información de estado de instancia de flujo de trabajo utilizando el algoritmo GZip antes de guardar el información en la base de datos de persistencia. Los valores permitidos para esta propiedad son: GZip y ninguno. El valor predeterminado es None. En la lista siguiente se describen estas opciones.  
  
1. **GZip**. El proveedor de persistencia codifica la información de estado mediante el algoritmo del GZip antes de conservar la información de estado en la base de datos de persistencia.  
  
2. **Ninguno**. El proveedor de persistencia no codifica la información de estado antes de guardar la información en la base de datos de persistencia.  
  
 Codificar la información de estado de la instancia de flujo de trabajo mediante GZip reduce el consumo de memoria en SQL Database y también el del consumo de la red si la base de datos reside en un equipo diferente en la red del equipo en el que el host de servicio de flujo de trabajo se está ejecutando. Un Consejo general consiste en establecer el **opción de codificación de la instancia** propiedad **ninguno** si el estado de la instancia de flujo de trabajo es pequeño.
