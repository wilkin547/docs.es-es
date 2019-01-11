---
title: Campo s_isDebuggerCheckDisabledForTestPurposes
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ada3abcccac4244819cfbef1101a770761df6a50
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221926"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>Campo s_isDebuggerCheckDisabledForTestPurposes

Este campo privado en la `System.Windows.Diagnostics.VisualDiagnostics` clase se usa Visual Studio para determinar si se realizará una comprobación interna de un depurador activo.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API en el `System.Windows.Diagnostics.VisualDiagnostics` clase solo están disponibles cuando una aplicación se ejecuta bajo un depurador. Establecer `s_isDebuggerCheckDisabledForTestPurposes` a `true` para tener acceso a las API fuera de un depurador.  
>   
>  Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.  

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Windows.Diagnostics>

**Ensamblado:** PresentationCore (en PresentationCore.dll)

**Versiones de .NET framework:** Disponible desde la versión 4.6.