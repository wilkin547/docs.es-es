---
title: s_isDebuggerCheckDisabledForTestPurposes campo
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
robots: noindex,nofollow
ms.openlocfilehash: fbbd8d33ea163efaad1417ab4a1435df729e4897
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes campo

Este campo privado en la `System.Windows.Diagnostics.VisualDiagnostics` clase se utiliza Visual Studio para determinar si se realizará una comprobación interna de un depurador activo.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API en el `System.Windows.Diagnostics.VisualDiagnostics` clase solo están disponibles cuando una aplicación se ejecuta bajo un depurador. Establecer `s_isDebuggerCheckDisabledForTestPurposes` a `true` para tener acceso a las API fuera de un depurador.  
>   
>  Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.  

## <a name="requirements"></a>Requisitos

**Namespace:** <xref:System.Windows.Diagnostics>

**Ensamblado:** PresentationCore (en PresentationCore.dll)

**Versiones de .NET framework:** disponible desde la versión 4.6.
