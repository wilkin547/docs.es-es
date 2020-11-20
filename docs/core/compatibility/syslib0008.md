---
title: Advertencia SYSLIB0008
description: Obtenga información sobre la obsolescencia que genera la advertencia en tiempo de compilación SYSLIB0008.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440600"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008: CreatePdbGenerator no es compatible

La API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> se ha marcado como obsoleta a partir de .NET 5.0. El empleo de esta API genera una advertencia `SYSLIB0008` en tiempo de compilación.

## <a name="suppress-the-warning"></a>Supresión de la advertencia

Si no puede cambiar el código, puede suprimir la advertencia por medio de una directiva `#pragma` o la opción de configuración del proyecto `<NoWarn>`. Para obtener ejemplos, vea [Supresión de advertencias](syslib-obsoletions.md#suppress-warnings).
