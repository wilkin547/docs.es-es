---
title: "Identifying Functions in DLLs | Microsoft Docs"
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
  - "platform invoke, identifying functions"
  - "COM interop, DLL functions"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "interoperation with unmanaged code, DLL functions"
  - "interoperation with unmanaged code, platform invoke"
  - "identifying DLL functions"
  - "DLL functions"
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Identifying Functions in DLLs
La identidad de una función de un archivo DLL está formada por los siguientes elementos:  
  
-   Nombre de la función u ordinal  
  
-   Nombre del archivo DLL donde se puede encontrar la implementación  
  
 Por ejemplo, si se especifica la función **MessageBox** en el archivo User32.dll, se identifica la función \(**MessageBox**\) y su ubicación \(User32.dll, User32 o user32\).  La interfaz de programación de aplicaciones de Microsoft Windows \(API Win32\) puede contener dos versiones de cada función que controla caracteres y cadenas: una versión ANSI de caracteres de 1 byte y una versión Unicode de caracteres de 2 bytes.  Si no se especifica, el juego de caracteres, representado por el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, toma el valor predeterminado de ANSI.  Algunas funciones pueden tener más de dos versiones.  
  
 **MessageBoxA** es el punto de entrada ANSI para la función **MessageBox**; la versión Unicode es **MessageBoxW**.  Es posible enumerar nombres de función para un archivo DLL específico, como user32.dll, mediante la ejecución de diversas herramientas de la línea de comandos.  Se puede utilizar, por ejemplo, `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` para obtener nombres de función.  
  
 Es posible cambiar el nombre de una función no administrada en el código, siempre y cuando se asigne el nuevo nombre al punto de entrada original del archivo DLL.  Para obtener instrucciones acerca de la forma de cambiar el nombre de una función no administrada de un archivo DLL en código fuente administrado, vea [Especificar un punto de entrada](../../../docs/framework/interop/specifying-an-entry-point.md).  
  
 La invocación de plataforma permite controlar una parte importante del sistema operativo llamando a funciones de la API Win32 y de otros archivos DLL.  Además de la API Win32, hay muchas otras API y archivos DLL disponibles a través de la invocación de plataforma.  
  
 En la tabla siguiente se describen varios archivos DLL de la API Win32 que se utilizan con frecuencia.  
  
|Archivo DLL|Descripción del contenido|  
|-----------------|-------------------------------|  
|GDI32.dll|Funciones de la interfaz de dispositivo gráfico \(GDI\) para la salida de dispositivos, como las funciones de administración de fuentes y dibujos.|  
|Kernel32.dll|Funciones del sistema operativo de bajo nivel para la administración de memoria y el control de recursos.|  
|User32.dll|Funciones de administración de Windows para el control de mensajes, los temporizadores, los menús y las comunicaciones.|  
  
 Para obtener la documentación completa de la API Win32, vea Platform SDK.  Para obtener ejemplos que muestren cómo construir declaraciones .NET que se utilizan con la invocación de plataforma, vea [Cálculo de referencias de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## Vea también  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [Specifying an Entry Point](../../../docs/framework/interop/specifying-an-entry-point.md)   
 [Creating a Class to Hold DLL Functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)