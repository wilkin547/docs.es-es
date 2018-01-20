---
title: "Habilitar la depuración de adjuntos JIT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71b2e95076edbda3a67a84c9185d8b689c158e12
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="enabling-jit-attach-debugging"></a>Habilitar la depuración de adjuntos JIT
La depuración de adjuntos JIT es la frase usada para describir el hecho de adjuntar un depurador a un proceso cuando se detectan errores, o se puede desencadenar mediante métodos o funciones concretos.  
  
 La depuración de adjuntos JIT se usa en las siguientes condiciones de error:  
  
-   Excepciones no controladas (el código nativo y administrado).  
  
-   Método <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o función [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) (familia Windows 7).  
  
-   Errores irrecuperables de runtime.  
  
 La depuración de adjuntos JIT también se desencadena mediante llamadas a los métodos y las funciones siguientes:  
  
-   Método <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.  
  
-   Método <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.  
  
-   [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) (función) (Win32).  
  
 Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework proporcionaba claves del Registro independientes para controlar el comportamiento de los depuradores administrados y nativos. A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], el control se consolida en una única clave del Registro: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Los valores que puede establecer para esa clave determinan si se invoca un depurador y, de ser así, si se invoca con un cuadro de diálogo que necesita interacción del usuario. Para obtener información acerca de cómo establecer esta clave del registro, consulte [Configuring Automatic Debugging](http://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Vea también  
 [Depurar, trazar y generar perfiles](../../../docs/framework/debug-trace-profile/index.md)  
 [Facilitar la depuración de una imagen](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 [Habilitar la generación de perfiles](http://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
