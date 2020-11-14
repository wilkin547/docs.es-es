---
title: Conversión de cadenas en tipos
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
ms.openlocfilehash: 3d23fa9c7ecc3593f03f70dbd5ea7bda841e8f4f
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400858"
---
# <a name="parse-strings-in-net"></a>Análisis de cadenas en .NET

Una operación de *análisis* convierte una cadena que representa un tipo base de .NET en dicho tipo base. Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora. El método que se usa normalmente para realizar una operación de análisis es el método `Parse`. Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones. Del mismo modo que el formato usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo se interpreta una representación de cadena. Para más información, consulte [Tipos de formato](formatting-types.md).

## <a name="in-this-section"></a>En esta sección
 [Análisis de cadenas numéricas](parsing-numeric.md)\
 Se describe cómo convertir cadenas en tipos numéricos de .NET.

 [Análisis de cadenas de fecha y hora](parsing-datetime.md)\
 Se describe cómo convertir cadenas en tipos **DateTime** de .NET.

 [Análisis de otras cadenas](parsing-other.md)\
 Se describe cómo convertir cadenas en tipos **carácter** , **booleano** y **enumeración**.

## <a name="related-sections"></a>Secciones relacionadas
 [Aplicar formato a tipos](formatting-types.md)\
 Se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.

 [Conversión de tipos en .NET](type-conversion.md)\
 Se describe cómo convertir tipos.
