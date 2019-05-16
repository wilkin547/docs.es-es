---
title: Campo s_isDebuggerCheckDisabledForTestPurposes
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ad9bc0ecf4b7a8e5f3ef13fdff5aa59ca8915922
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634658"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>Campo s_isDebuggerCheckDisabledForTestPurposes

Este campo privado en la `System.Windows.Diagnostics.VisualDiagnostics` clase se usa Visual Studio para determinar si se realizará una comprobación interna de un depurador activo.

## <a name="syntax"></a>Sintaxis

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> Las API en el `System.Windows.Diagnostics.VisualDiagnostics` clase solo están disponibles cuando una aplicación se ejecuta bajo un depurador. Establecer `s_isDebuggerCheckDisabledForTestPurposes` a `true` para tener acceso a las API fuera de un depurador.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Windows.Diagnostics>

**Ensamblado:** PresentationCore (en PresentationCore.dll)

**Versiones de .NET framework:** Disponible desde la versión 4.6.
