---
title: Analizar cadenas en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: e4bf14981e538d95aebac3b0f36d38b61747989f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73084313"
---
# <a name="parsing-strings-in-net"></a>Analizar cadenas en .NET
Una operación de análisis convierte una cadena que representa un tipo base de .NET en dicho tipo base. Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora. El método que se usa normalmente para realizar una operación de análisis es el método `Parse`. Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones. Del mismo modo que el formato usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo se interpreta una representación de cadena. Para obtener más información, consulte [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Análisis de cadenas numéricas](../../../docs/standard/base-types/parsing-numeric.md)  
 Se describe cómo convertir cadenas en tipos numéricos de .NET.  
  
 [Análisis de cadenas de fecha y hora](../../../docs/standard/base-types/parsing-datetime.md)  
 Se describe cómo convertir cadenas en tipos **DateTime** de .NET.  
  
 [Análisis de otras cadenas](../../../docs/standard/base-types/parsing-other.md)  
 Se describe cómo convertir cadenas en tipos **carácter**, **booleano** y **enumeración**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)  
 Se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.  
  
 [Conversión de tipos en .NET](../../../docs/standard/base-types/type-conversion.md)  
 Se describe cómo convertir tipos.  
  
 [Tipos base](../../../docs/standard/base-types/index.md)  
 Se describen las operaciones comunes que se pueden realizar en tipos base de .NET.
