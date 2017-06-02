---
title: "Enabling JIT-Attach Debugging | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "JIT-attach debugging"
  - "debugging [.NET Framework], JIT-attach debugging"
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Enabling JIT-Attach Debugging
Habilitar la depuración JIT es la frase utilizada para describir el hecho de adjuntar un depurador a un proceso cuando se detectan errores, aunque también se puede desencadenar mediante métodos o funciones concretos.  
  
 Habilitar la depuración JIT se utiliza en las siguientes condiciones de error:  
  
-   Excepciones no controladas \(el código nativo y administrado\).  
  
-   método o función [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) \(familia de<xref:System.Environment.FailFast%2A?displayProperty=fullName> de Windows 7\).  
  
-   Errores irrecuperables de runtime.  
  
 Habilitar la depuración JIT también se desencadena mediante llamadas a los métodos y las funciones siguientes:  
  
-   Método <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName>.  
  
-   Método <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName>.  
  
-   [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) función \(Win32\).  
  
 Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework proporcionaba claves del Registro independientes para controlar el comportamiento de los depuradores nativos y administrados.  A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], el control se consolida en una sola clave del Registro: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\Current Version\\AeDebug.  Los valores que se pueden establecer para esa clave determinan si se invoca un depurador y, en caso afirmativo, si se invoca con un cuadro de diálogo que requiera interacción con el usuario.  Para obtener información sobre cómo establecer esta clave del Registro, [Depuración automática de configuración](http://go.microsoft.com/fwlink/?LinkId=181767) vea en MSDN Library.  
  
## Vea también  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [Facilitar la depuración de una imagen](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Enabling Profiling](http://msdn.microsoft.com/es-es/3b669676-f0e0-4ebf-8674-68986dd2020d)