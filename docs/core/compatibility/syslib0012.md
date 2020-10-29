---
title: Advertencia SYSLIB0012
description: Obtenga información sobre las obsolescencias que generan la advertencia en tiempo de compilación SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2ed93b6eefbaa861faca319f0cc9bf19ac741f3b
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333169"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012: Assembly.CodeBase y Assembly.EscapedCodeBase están obsoletos

Las siguientes API se han marcado como obsoletas a partir de .NET 5.0. Su empleo en el código genera una advertencia `SYSLIB0012` en tiempo de compilación.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

Solución alternativa

Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar.
