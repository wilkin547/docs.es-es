---
title: Analizar cadenas en .NET
description: Conozca el análisis de cadenas en .NET. El análisis convierte una cadena que representa un tipo base de .NET en ese tipo base. El análisis es la operación inversa de la aplicación de formato.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 5e297c8f689fdabc268ee6e269a7969155befe7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769293"
---
# <a name="parsing-strings-in-net"></a>Analizar cadenas en .NET
Una operación de análisis convierte una cadena que representa un tipo base de .NET en dicho tipo base. Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora. El método que se usa normalmente para realizar una operación de análisis es el método `Parse`. Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones. Del mismo modo que el formato usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo se interpreta una representación de cadena. Para obtener más información, consulte [Aplicar formato a tipos](formatting-types.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Análisis de cadenas numéricas](parsing-numeric.md)  
 Se describe cómo convertir cadenas en tipos numéricos de .NET.  
  
 [Análisis de cadenas de fecha y hora](parsing-datetime.md)  
 Se describe cómo convertir cadenas en tipos **DateTime** de .NET.  
  
 [Análisis de otras cadenas](parsing-other.md)  
 Se describe cómo convertir cadenas en tipos **carácter**, **booleano** y **enumeración**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Aplicación de formato a tipos](formatting-types.md)  
 Se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.  
  
 [Conversión de tipos en .NET](type-conversion.md)  
 Se describe cómo convertir tipos.
