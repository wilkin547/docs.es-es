---
title: Advertencia SYSLIB0008
description: Obtenga información sobre la obsolescencia que genera la advertencia en tiempo de compilación SYSLIB0008.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b573f4b28cdf79107395f5cb38a4226d0ccc11e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596397"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008: CreatePdbGenerator no es compatible

La API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> se ha marcado como obsoleta a partir de .NET 5.0. El empleo de esta API genera una advertencia `SYSLIB0008` en tiempo de compilación.

## <a name="suppress-the-warning"></a>Supresión de la advertencia

Si no puede cambiar el código, puede suprimir la advertencia por medio de una directiva `#pragma` o la opción de configuración del proyecto `<NoWarn>`. Para obtener ejemplos, vea [Supresión de advertencias](../syslib-obsoletions.md#suppress-warnings).
