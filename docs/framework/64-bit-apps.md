---
title: Aplicaciones de 64 bits | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [C++], 64-bit
- 64-bit applications [C++]
- 64-bit programming [C++]
ms.assetid: fd4026bc-2c3d-4b27-86dc-ec5e96018181
caps.latest.revision: 53
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3d1ddfa9842909a491af2541c9ac770989fc2164
ms.lasthandoff: 04/18/2017

---
# <a name="64-bit-applications"></a>Aplicaciones de 64 bits
Al compilar una aplicación, puede especificar que debe ejecutarse en un sistema operativo Windows de 64 bits como una aplicación nativa o bajo WOW64 (Windows de 32 bits en Windows de 64 bits). WOW64 es un entorno de compatibilidad que permite a una aplicación de 32 bits ejecutarse en un sistema de 64 bits. WOW64 se incluye en todas las versiones de 64 bits del sistema operativo Windows.  
  
## <a name="running-32-bit-vs-64-bit-applications-on-windows"></a>Ejecutar en Windows aplicaciones de 32 bits frente a aplicaciones de 64 bits  
 Todas las aplicaciones compiladas con .NET Framework 1.0 o 1.1 se tratan como aplicaciones de 32 bits en un sistema operativo de 64 bits y siempre se ejecutan bajo WOW64 y el Common Language Runtime (CLR) de 32 bits. Las aplicaciones de 32 bits que se compilan en [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)] o versiones posteriores también se ejecutan bajo WOW64 en sistemas de 64 bits.  
  
 Visual Studio instala la versión de 32 bits de CLR en un equipo x86, y la versión de 32 bits y la versión de 64 bits apropiada de CLR en un equipo Windows de 64 bits. (Dado que Visual Studio es una aplicación de 32 bits, cuando se instala en un sistema de 64 bits, se ejecuta bajo WOW64).  
  
> [!NOTE]
>  Debido al diseño de emulación de x86 y al subsistema de WOW64 para la familia de procesadores Itanium, la ejecución de las aplicaciones está restringida a un único procesador. Estos factores reducen el rendimiento y la escalabilidad de las aplicaciones de 32 bits de .NET Framework que se ejecutan en sistemas basados en Itanium. Se recomienda usar [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)], que incluye compatibilidad nativa con 64 bits para sistemas basados en Itanium, para un mayor rendimiento y escalabilidad.  
  
 De forma predeterminada, cuando ejecute una aplicación administrada de 64 bits en un sistema operativo Windows de 64 bits, puede crear un objeto de no más de 2 gigabytes (GB). Sin embargo, en [!INCLUDE[net_v45](../../includes/net-v45-md.md)], puede aumentar este límite.  Para más información, consulte [Elemento \<gcAllowVeryLargeObjects>](../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md).  
  
 Muchos ensamblados se ejecutan de forma idéntica en el CLR de 32 bits y el CLR de 64 bits. Sin embargo, algunos programas pueden comportarse de manera diferente, dependiendo de CLR, si contienen uno o varios de los elementos siguientes:  
  
-   Estructuras que contengan miembros cuyo tamaño varía según la plataforma, (por ejemplo, cualquier tipo de puntero).  
  
-   Aritmética de punteros que incluya tamaños constantes.  
  
-   Invocación incorrecta de la plataforma o declaraciones COM que utilicen `Int32` para los controladores en lugar de `IntPtr`.  
  
-   Código que convierte `IntPtr` en `Int32`.  
  
 Para más información sobre cómo migrar una aplicación de 32 bits para que se ejecute en el CLR de 64 bits, vea [Migrating 32-bit Managed Code to 64-bit](http://go.microsoft.com/fwlink/?LinkId=150542) (Migración de código administrado de 32 bits a 64 bits) en MSDN Library.  
  
## <a name="general-64-bit-programming-information"></a>Información general de programación de 64 bits  
 Para obtener información general sobre la programación de 64 bits, vea los siguientes documentos:  
  
-   Para más información sobre la versión de 64 bits de CLR en un equipo Windows de 64 bits, vea el [Centro para desarrolladores de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37079) en el sitio web de MSDN.  
  
-   En la documentación de [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)], vea [Programming Guide for 64-bit Windows](http://go.microsoft.com/fwlink/p/?LinkId=253512) (Guía de programación para Windows de 64 bits).  
  
-   Para información sobre cómo descargar una versión de 64 bits de CLR, vea [.NET Framework Developer Center Downloads](http://go.microsoft.com/fwlink/?LinkId=50953) (Descargas del centro para desarrolladores de .NET Framework) en el sitio web de MSDN.  
  
-   Para información sobre la compatibilidad de Visual Studio para crear aplicaciones de 64 bits, consulte [Compatibilidad de 64 bits del IDE de Visual Studio](http://msdn.microsoft.com/library/b08ff3ad-c6fd-468f-94d5-01a61aab6833).  
  
## <a name="compiler-support-for-creating-64-bit-applications"></a>Compatibilidad del compilador para crear aplicaciones de 64 bits  
 De forma predeterminada, cuando se usa .NET Framework para compilar una aplicación en un equipo de 32 o 64 bits, la aplicación se ejecutará en un equipo de 64 bits como una aplicación nativa (es decir, no bajo WOW64). En la tabla siguiente se enumeran los documentos que explican cómo usar los compiladores de Visual Studio para crear aplicaciones de 64 bits que se ejecuten como nativas, bajo WOW64, o en ambas situaciones.  
  
|Compilador|Opción del compilador|  
|--------------|---------------------|  
|Visual Basic|[/platform (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/platform.md)|  
|Visual C#|[/platform (opciones del compilador de C#)](~/docs/csharp/language-reference/compiler-options/platform-compiler-option.md)|  
|Visual C++|Puede crear aplicaciones del Lenguaje Intermedio de Microsoft (MSIL) independientes de la plataforma utilizando **/clr:safe**. Para obtener más información, consulte [/clr (Compilación de Common Language Runtime)](http://msdn.microsoft.com/library/fec5a8c0-40ec-484c-a213-8dec918c1d6c).<br /><br /> Visual C++ incluye un compilador independiente para cada sistema operativo de 64 bits. Para más información sobre cómo utilizar Visual C++ para crear aplicaciones nativas que se ejecuten en un sistema operativo Windows de 64 bits, vea [Programación de 64 bits con Visual C++](http://msdn.microsoft.com/library/h2k70f3s\(v=vs.80\)).|  
  
## <a name="determining-the-status-of-an-exe-file-or-dll-file"></a>Determinar el estado de un archivo .exe o .dll  
 Para determinar si un archivo .exe o .dll está diseñado para que se ejecute solo en una plataforma específica o bajo WOW64, use [CorFlags.exe (herramienta de conversión CorFlags)](../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md) sin ninguna opción. También puede usar CorFlags.exe para cambiar el estado de la plataforma de un archivo .exe o .dll. El encabezado CLR de un ensamblado de Visual Studio tiene el número principal de versión de runtime establecido en 2 y el número secundario de versión de runtime establecido en 5. Las aplicaciones que tienen el número secundario de versión de runtime establecido en 0 se tratan como aplicaciones heredadas y siempre se ejecutan bajo WOW64.  
  
 Para comprobar mediante programación si un archivo .exe o .dll está diseñado para que se ejecute solo en una plataforma específica o bajo WOW64, utilice el método <xref:System.Reflection.Module.GetPEKind%2A?displayProperty=fullName>.
