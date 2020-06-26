---
title: Habilitar la depuración de adjuntos JIT
description: Habilite la depuración de adjuntos Just-in-Time (JIT) para adjuntar un depurador a un proceso cuando se encuentre con errores. Se puede desencadenar mediante determinados métodos o funciones.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
ms.openlocfilehash: d1190c51a9cc6b5322ec832e0d35bc01dc855b12
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416049"
---
# <a name="enabling-jit-attach-debugging"></a>Habilitar la depuración de adjuntos JIT
La depuración de adjuntos JIT es la frase usada para describir el hecho de adjuntar un depurador a un proceso cuando se detectan errores, o se puede desencadenar mediante métodos o funciones concretos.  
  
 La depuración de adjuntos JIT se usa en las siguientes condiciones de error:  
  
- Excepciones no controladas (el código nativo y administrado).  
  
- Método <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o función [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) (familia Windows 7).  
  
- Errores irrecuperables de runtime.  
  
 La depuración de adjuntos JIT también se desencadena mediante llamadas a los métodos y las funciones siguientes:  
  
- Método <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.  
  
- Método <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.  
  
- [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) (función) (Win32).  
  
 Antes del .NET Framework 4, el .NET Framework proporcionó claves de registro independientes para controlar el comportamiento de los depuradores administrados y nativos. A partir de la .NET Framework 4, el control se consolida en una única clave del registro: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Los valores que puede establecer para esa clave determinan si se invoca un depurador y, de ser así, si se invoca con un cuadro de diálogo que necesita interacción del usuario. Para obtener información acerca de cómo establecer esta clave del registro, vea configuración de la [depuración automática](/windows/win32/debug/configuring-automatic-debugging).  
  
## <a name="see-also"></a>Consulte también

- [Depurar, trazar y generar perfiles](index.md)
- [Facilitar la depuración de una imagen](making-an-image-easier-to-debug.md)
