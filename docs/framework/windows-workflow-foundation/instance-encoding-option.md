---
description: 'Más información acerca de: opción de codificación de instancias'
title: Opción de codificación de instancias
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 8cca7fd536673ca99b1014173e172508e3d97b7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631169"
---
# <a name="instance-encoding-option"></a>Opción de codificación de instancias

La propiedad **opción de codificación de instancias** del almacén de instancias de flujo de trabajo de SQL le permite especificar si el proveedor de persistencia de SQL debe comprimir la información de estado de la instancia de flujo de trabajo mediante el algoritmo gzip antes de guardar la información en la base de datos de persistencia. Los valores permitidos para esta propiedad son: GZip y Ninguno. El valor predeterminado es Ninguno. En la lista siguiente se describen estas opciones.  
  
1. **Gzip**. El proveedor de persistencia codifica la información de estado mediante el algoritmo del GZip antes de conservar la información de estado en la base de datos de persistencia.  
  
2. **No**. El proveedor de persistencia no codifica la información de estado antes de guardar la información en la base de datos de persistencia.  
  
 Codificar la información de estado de la instancia de flujo de trabajo mediante GZip reduce el consumo de memoria en SQL Database y también el del consumo de la red si la base de datos reside en un equipo diferente en la red del equipo en el que el host de servicio de flujo de trabajo se está ejecutando. Una guía general consiste en establecer la propiedad **opción de codificación de instancia** en **ninguno** si el estado de la instancia de flujo de trabajo es pequeño.
