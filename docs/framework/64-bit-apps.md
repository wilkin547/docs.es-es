---
title: "Aplicaciones de 64 bits | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones de 64 bits [C++]"
  - "programación de 64 bits [C++]"
  - "aplicaciones [C++], 64 bits"
ms.assetid: fd4026bc-2c3d-4b27-86dc-ec5e96018181
caps.latest.revision: 53
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 53
---
# Aplicaciones de 64 bits
Al compilar una aplicación, puede especificar que debe ejecutarse en un sistema operativo Windows de 64 bits como una aplicación nativa o bajo WOW64 \(Windows de 32 bits en Windows de 64 bits\).  WOW64 es un entorno de compatibilidad que permite a una aplicación de 32 bits ejecutarse en un sistema de 64 bits.  WOW64 se incluye en todas las versiones de 64 bits del sistema operativo Windows.  
  
## Ejecutar en Windows aplicaciones de 32 bitsfrente a aplicaciones de 64 bits  
 Todas las aplicaciones compiladas con .NET Framework 1.0 o 1.1 se tratan como aplicaciones de 32 bits en un sistema operativo de 64 bits y siempre se ejecutan bajo WOW64 y el Common Language Runtime \(CLR\) de 32 bits.  Las aplicaciones de 32 bits que se compilan en [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)] o versiones posteriores también se ejecutan bajo WOW64 en sistemas de 64 bits.  
  
 Visual Studio instala la versión de 32 bits de CLR en un equipo x86, y la versión de 32 bits y la versión de 64 bits apropiada de CLR en un equipo Windows de 64 bits.  \(Dado que Visual Studio es una aplicación de 32 bits, cuando se instala en un sistema de 64 bits, se ejecuta bajo WOW64\).  
  
> [!NOTE]
>  Debido al diseño de emulación de x86 y al subsistema de WOW64 para la familia de procesadores Itanium, la ejecución de las aplicaciones está restringida a un único procesador.  Estos factores reducen el rendimiento y la escalabilidad de las aplicaciones de 32 bits de .NET Framework que se ejecutan en sistemas basados en Itanium.  Se recomienda usar [!INCLUDE[net_v40_long](../../includes/net-v40-long-md.md)], que incluye compatibilidad nativa con 64 bits para sistemas basados en Itanium, para un mayor rendimiento y escalabilidad.  
  
 De forma predeterminada, cuando ejecute una aplicación administrada de 64 bits en un sistema operativo Windows de 64 bits, puede crear un objeto de no más de 2 gigabytes \(GB\).  Sin embargo, en [!INCLUDE[net_v45](../../includes/net-v45-md.md)], puede aumentar este límite.  Para obtener más información, vea el elemento [\<gcAllowVeryLargeObjects\>](../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md).  
  
 Muchos ensamblados se ejecutan de forma idéntica en el CLR de 32 bits y el CLR de 64 bits.  Sin embargo, algunos programas pueden comportarse de manera diferente, dependiendo de CLR, si contienen uno o varios de los elementos siguientes:  
  
-   Estructuras que contengan miembros cuyo tamaño varía según la plataforma, \(por ejemplo, cualquier tipo de puntero\).  
  
-   Aritmética de punteros que incluya tamaños constantes.  
  
-   Invocación incorrecta de la plataforma o declaraciones COM que utilicen `Int32` para los controladores en lugar de `IntPtr`.  
  
-   Código que convierte `IntPtr` en `Int32`.  
  
 Para obtener más información acerca de cómo migrar una aplicación de 32 bits para que se ejecute en un CLR de 64 bits, consulte [Migrar código administrado de 32 bits a 64 bits](http://go.microsoft.com/fwlink/?LinkId=150542) en MSDN Library.  
  
## Información general de programación de 64 bits  
 Para obtener información general sobre la programación de 64 bits, vea los siguientes documentos:  
  
-   Para obtener más información acerca de la versión de 64 bits del CLR en un equipo Windows de 64 bits, consulte [Centro de desarrollo de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37079)en el sitio web de MSDN.  
  
-   En la documentación de [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)], consulte [Guía de programación para Windows de 64 bits](http://go.microsoft.com/fwlink/p/?LinkId=253512).  
  
-   Para obtener información acerca de cómo descargar una versión de 64 bits del CLR, consulte [Descargas del centro de desarrollo de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=50953) en el sitio web de MSDN.  
  
-   Para obtener información acerca de la compatibilidad de Visual Studio para crear aplicaciones de 64 bits, consulte [Compatibilidad de 64 bits del IDE de Visual Studio](../Topic/Visual%20Studio%20IDE%2064-Bit%20Support.md).  
  
## Compatibilidad del compilador para crear aplicaciones de 64 bits  
 De forma predeterminada, cuando se usa .NET Framework para compilar una aplicación en un equipo de 32 o 64 bits, la aplicación se ejecutará en un equipo de 64 bits como una aplicación nativa \(es decir, no bajo WOW64\).  En la tabla siguiente se enumeran los documentos que explican cómo usar los compiladores de Visual Studio para crear aplicaciones de 64 bits que se ejecuten como nativas, bajo WOW64, o en ambas situaciones.  
  
|Compilador|Opción del compilador|  
|----------------|---------------------------|  
|Visual Basic|[\/platform](../Topic/-platform%20\(Visual%20Basic\).md)|  
|Visual C\#|[\/platform \(Specify Output Platform\)](../Topic/-platform%20\(C%23%20Compiler%20Options\).md)|  
|Visual C\+\+|Puede crear aplicaciones del Lenguaje Intermedio de Microsoft \(MSIL\) independientes de la plataforma utilizando **\/clr:safe**.  Para obtener más información, consulte [\/clr \(Compilación de Common Language Runtime\)](../Topic/-clr%20\(Common%20Language%20Runtime%20Compilation\).md).<br /><br /> Visual C\+\+ incluye un compilador independiente para cada sistema operativo de 64 bits.  Para obtener más información acerca de cómo utilizar Visual C\+\+ para crear aplicaciones nativas que se ejecuten en un sistema operativo Windows de 64 bits, consulte [Programación de 64 bits](http://msdn.microsoft.com/library/h2k70f3s\(v=vs.80\)).|  
  
## Determinar el estado de un archivo .exe o .dll  
 Para determinar si un archivo .exe o .dll está diseñado para que se ejecute solo en una plataforma específica o bajo WOW64, use la [CorFlags.exe \(CorFlags Conversion Tool\)](../../docs/framework/tools/corflags-exe-corflags-conversion-tool.md) sin ninguna opción.  También puede usar CorFlags.exe para cambiar el estado de la plataforma de un archivo .exe o .dll.  El encabezado CLR de un ensamblado de Visual Studio tiene el número principal de versión de runtime establecido en 2 y el número secundario de versión de runtime establecido en 5.  Las aplicaciones que tienen el número secundario de versión de runtime establecido en 0 se tratan como aplicaciones heredadas y siempre se ejecutan bajo WOW64.  
  
 Para comprobar mediante programación si un archivo .exe o .dll está diseñado para que se ejecute solo en una plataforma específica o bajo WOW64, utilice el método <xref:System.Reflection.Module.GetPEKind%2A?displayProperty=fullName>.