---
title: Advertencia SYSLIB0012
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dc139d5c5cb6d6a34d161147b350b3324d15117e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440587"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012: Assembly.CodeBase y Assembly.EscapedCodeBase están obsoletos

Las siguientes API se han marcado como obsoletas a partir de .NET 5.0. Su empleo en el código genera una advertencia `SYSLIB0012` en tiempo de compilación.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a>Soluciones alternativas

Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar.

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]
