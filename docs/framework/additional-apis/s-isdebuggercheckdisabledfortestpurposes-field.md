---
title: s_isDebuggerCheckDisabledForTestPurposes campo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name: System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location: PresentationCore.dll
api_type: Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.openlocfilehash: 97e5d32bff3e3150b56e8d9492aacc40f09f2afe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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

**Namespace:**<xref:System.Windows.Diagnostics>

**Ensamblado:** PresentationCore (en PresentationCore.dll)

**Versiones de .NET framework:** disponible desde la versión 4.6.
