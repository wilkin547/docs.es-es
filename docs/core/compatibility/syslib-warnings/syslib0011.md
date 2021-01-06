---
title: Advertencia SYSLIB0011
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0011.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 36292cc5314e2b7677d705780880b7e25ae0dfb6
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596409"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a><span data-ttu-id="ac715-103">SYSLIB0011: la serialización BinaryFormatter está obsoleta</span><span class="sxs-lookup"><span data-stu-id="ac715-103">SYSLIB0011: BinaryFormatter serialization is obsolete</span></span>

<span data-ttu-id="ac715-104">Debido a [vulnerabilidades de seguridad](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, las siguientes API se han marcado como obsoletas a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="ac715-104">Due to [security vulnerabilities](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="ac715-105">Su empleo en el código genera una advertencia `SYSLIB0011` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ac715-105">Using them in code generates warning `SYSLIB0011` at compile time.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="ac715-106">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="ac715-106">Workarounds</span></span>

<span data-ttu-id="ac715-107">Considere la posibilidad de usar <xref:System.Text.Json.JsonSerializer> o <xref:System.Xml.Serialization.XmlSerializer> en lugar de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="ac715-107">Consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer> instead of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span>

<span data-ttu-id="ac715-108">Para más información sobre las acciones recomendadas, consulte [Resolución de errores de desactivación y deshabilitación de BinaryFormatter](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="ac715-108">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="ac715-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac715-109">See also</span></span>

- [<span data-ttu-id="ac715-110">Resolución de errores de obsolescencia y deshabilitación de BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="ac715-110">Resolving BinaryFormatter obsoletion and disablement errors</span></span>](https://aka.ms/binaryformatter)
- [<span data-ttu-id="ac715-111">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ac715-111">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
