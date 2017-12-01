---
title: Analizar cadenas en .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a>Analizar cadenas en .NET
Una operación de análisis convierte una cadena que representa un tipo base de .NET en dicho tipo base. Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora. El método que se usa normalmente para realizar una operación de análisis es el método `Parse`. Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones. Al igual que el formato usa un objeto que implementa el <xref:System.IFormatProvider> interfaz para proporcionar información de formato de cuenta de la referencia cultural, análisis también utiliza un objeto que implementa el <xref:System.IFormatProvider> interfaz para determinar cómo interpretar una representación de cadena . Para obtener más información, consulte [Formatting Types](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Análisis de cadenas numéricas](../../../docs/standard/base-types/parsing-numeric.md)  
 Describe cómo convertir cadenas en tipos numéricos. NET.  
  
 [Análisis de cadenas de fecha y hora](../../../docs/standard/base-types/parsing-datetime.md)  
 Describe cómo convertir cadenas en .NET **DateTime** tipos.  
  
 [Análisis de otras cadenas](../../../docs/standard/base-types/parsing-other.md)  
 Describe cómo convertir cadenas en **Char**, **booleano**, y **Enum** tipos.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)  
 Describe los conceptos básicos de formato como especificadores de formato y proveedores de formato.  
  
 [Conversión de tipos en .NET](../../../docs/standard/base-types/type-conversion.md)  
 Describe cómo se convierten a tipos.  
  
 [Tipos base](../../../docs/standard/base-types/index.md)  
 Describe las operaciones habituales que pueden realizar en tipos base. NET.
