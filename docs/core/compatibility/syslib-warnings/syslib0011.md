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
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a><span data-ttu-id="2a17c-103">SYSLIB0011: la serialización BinaryFormatter está obsoleta</span><span class="sxs-lookup"><span data-stu-id="2a17c-103">SYSLIB0011: BinaryFormatter serialization is obsolete</span></span>

<span data-ttu-id="2a17c-104">Debido a [vulnerabilidades de seguridad](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="2a17c-104">Due to [security vulnerabilities](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="2a17c-105">Su empleo en el código genera una advertencia `SYSLIB0011` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="2a17c-105">Using them in code generates warning `SYSLIB0011` at compile time.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="2a17c-106">Soluciones</span><span class="sxs-lookup"><span data-stu-id="2a17c-106">Workarounds</span></span>

<span data-ttu-id="2a17c-107">Considere la posibilidad de usar <xref:System.Text.Json.JsonSerializer> o <xref:System.Xml.Serialization.XmlSerializer> en lugar de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="2a17c-107">Consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer> instead of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span>

<span data-ttu-id="2a17c-108">Para más información sobre las acciones recomendadas, consulte [Resolución de errores de desactivación y deshabilitación de BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="2a17c-108">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="2a17c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a17c-109">See also</span></span>

- [<span data-ttu-id="2a17c-110">Resolución de errores de obsolescencia y deshabilitación de BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="2a17c-110">Resolving BinaryFormatter obsoletion and disablement errors</span></span>](../../../standard/serialization/binaryformatter-security-guide.md)
- [<span data-ttu-id="2a17c-111">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2a17c-111">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
