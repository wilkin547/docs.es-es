---
title: Advertencia SYSLIB0011
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0011.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b363e565ce1143c162679c6b74621885378d7ff
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333170"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a>SYSLIB0011: la serialización BinaryFormatter está obsoleta

Debido a [vulnerabilidades de seguridad](../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, las siguientes API se han marcado como obsoletas a partir de .NET 5.0. Su empleo en el código genera una advertencia `SYSLIB0011` en tiempo de compilación.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workaround"></a>Solución alternativa

Considere la posibilidad de usar <xref:System.Text.Json.JsonSerializer> o <xref:System.Xml.Serialization.XmlSerializer> en lugar de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.

Para más información sobre las acciones recomendadas, consulte [Resolución de errores de desactivación y deshabilitación de BinaryFormatter](https://aka.ms/binaryformatter).

## <a name="see-also"></a>Vea también

- [Resolución de errores de obsolescencia y deshabilitación de BinaryFormatter](https://aka.ms/binaryformatter)
- [Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET](corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
