---
title: Advertencia SYSLIB0011
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0011.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 85b5e07b1ecd6852d8c8e93cc3e89ced4b021ef9
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189862"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a>SYSLIB0011: la serialización BinaryFormatter está obsoleta

Debido a [vulnerabilidades de seguridad](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, las siguientes API se han marcado como obsoletas a partir de .NET 5.0. Su empleo en el código genera una advertencia `SYSLIB0011` en tiempo de compilación.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a>Soluciones

Considere la posibilidad de usar <xref:System.Text.Json.JsonSerializer> o <xref:System.Xml.Serialization.XmlSerializer> en lugar de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.

Para más información sobre las acciones recomendadas, consulte [Resolución de errores de desactivación y deshabilitación de BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md).

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Vea también

- [Resolución de errores de obsolescencia y deshabilitación de BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md)
- [Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
