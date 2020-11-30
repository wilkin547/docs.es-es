---
title: Conversión de cadenas en tipos
description: Conozca el análisis de cadenas en .NET. El análisis convierte una cadena que representa un tipo base de .NET en ese tipo base. El análisis es la operación inversa de la aplicación de formato.
ms.date: 03/30/2017
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: a5c38c29a45a9ce6f8aed7205c5bd44bebb023c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683725"
---
# <a name="parse-strings-in-net"></a>Análisis de cadenas en .NET

Una operación de *análisis* convierte una cadena que representa un tipo base de .NET en dicho tipo base. Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora. El método que se usa normalmente para realizar una operación de análisis es el método `Parse`. Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones. Del mismo modo que el formato usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo se interpreta una representación de cadena. Para más información, consulte [Tipos de formato](formatting-types.md).

## <a name="in-this-section"></a>En esta sección

 [Análisis de cadenas numéricas](parsing-numeric.md)\
 Se describe cómo convertir cadenas en tipos numéricos de .NET.

 [Análisis de cadenas de fecha y hora](parsing-datetime.md)\
 Se describe cómo convertir cadenas en tipos **DateTime** de .NET.

 [Análisis de otras cadenas](parsing-other.md)\
 Se describe cómo convertir cadenas en tipos **carácter**, **booleano** y **enumeración**.

## <a name="related-sections"></a>Secciones relacionadas

 [Aplicar formato a tipos](formatting-types.md)\
 Se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.

 [Conversión de tipos en .NET](type-conversion.md)\
 Se describe cómo convertir tipos.
