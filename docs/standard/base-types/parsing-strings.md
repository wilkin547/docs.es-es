---
title: Analizar cadenas en .NET
description: Analizar cadenas en .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a>Analizar cadenas en .NET

Una operación de análisis convierte una cadena que representa un tipo base de .NET en dicho tipo base. Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora. El método que se usa normalmente para realizar una operación de análisis es el método `Parse`. Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones. Del mismo modo que el formato usa un objeto que implementa la interfaz [IFormatProvider](xref:System.IFormatProvider) para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz [IFormatProvider](xref:System.IFormatProvider) para determinar cómo se interpreta una representación de cadena. Para obtener más información, consulte [Aplicar formato a tipos en .NET](formatting-types.md).

## <a name="in-this-section"></a>En esta sección

[Analizar cadenas numéricas en .NET](parsing-numeric.md): se describe cómo convertir cadenas en tipos numéricos de .NET.

[Analizar cadenas de fecha y hora en .NET](parsing-datetime.md): se describe cómo convertir cadenas en tipos de .NET `DateTime`.

[Analizar otras cadenas en .NET](parsing-other.md): se describe cómo convertir cadenas en tipos [Char](xref:System.Char), [Boolean](xref:System.Boolean) y [Enum](xref:System.Enum).

[Aplicar formato a tipos en .NET](formatting-types.md): se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.

[Conversión de tipos en .NET](type-conversion.md): se describe cómo se convierten tipos.

[Trabajar con tipos base en .NET](index.md): se describen las operaciones comunes que se pueden realizar en tipos base de .NET.


