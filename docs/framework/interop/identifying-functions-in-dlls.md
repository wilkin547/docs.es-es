---
title: Identificar funciones en archivos DLL
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc160678817266dc649f60dc3f2cc77044c05691
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="identifying-functions-in-dlls"></a>Identificar funciones en archivos DLL
La identidad de una función DLL consta de los siguientes elementos:  
  
-   Nombre de la función u ordinal  
  
-   Nombre del archivo DLL en el que se puede encontrar la implementación  
  
 Por ejemplo, si se especifica la función **MessageBox** en el archivo User32.dll se identifica la función (**MessageBox**) y su ubicación (User32.dll, User32 o user32). La interfaz de programación de aplicaciones (API Win32) de Microsoft Windows puede contener dos versiones de cada función que controla caracteres y cadenas: una versión ANSI de caracteres de un byte y una versión Unicode de caracteres de dos bytes. Si no se especifica, el juego de caracteres (representado por el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>) es ANSI de manera predeterminada. Algunas funciones pueden tener más de dos versiones.  
  
 **MessageBoxA** es el punto de entrada ANSI para la función **MessageBox**; **MessageBoxW** es la versión de Unicode. Puede enumerar los nombres de función de un archivo DLL específico, como user32.dll, mediante la ejecución de una variedad de herramientas de línea de comandos. Por ejemplo, puede usar `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` para obtener los nombres de función.  
  
 Puede cambiar el nombre de una función no administrada por el nombre que quiera dentro del código siempre que se asigne el nombre nuevo al punto de entrada original en el archivo DLL. Para obtener instrucciones sobre cómo cambiar el nombre de una función DLL no administrada en código fuente administrado, vea [Especificar un punto de entrada](../../../docs/framework/interop/specifying-an-entry-point.md).  
  
 La invocación de plataforma permite controlar una parte importante del sistema operativo mediante la llamada a las funciones de la API Win32 y otros archivos DLL. Además de la API Win32, hay muchas otras API y archivos DLL disponibles a través de la invocación de plataforma.  
  
 En la tabla siguiente se describen varios archivos DLL que se usan habitualmente en la API Win32.  
  
|Archivo DLL|Descripción del contenido|  
|---------|-----------------------------|  
|GDI32.dll|Funciones de Interfaz de dispositivo gráfico (GDI) para salida de dispositivos, como las de dibujo y administración de fuentes.|  
|Kernel32.dll|Funciones de bajo nivel del sistema operativo para la administración de memoria y el control de recursos.|  
|User32.dll|Funciones de administración de Windows para el control de mensajes, temporizadores, menús y comunicaciones.|  
  
 Para obtener la documentación completa sobre la API Win32, vea Platform SDK. Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Vea también  
 [Consumir funciones DLL no administradas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [Especificar un punto de entrada](../../../docs/framework/interop/specifying-an-entry-point.md)  
 [Creación de una clase para contener funciones de archivos DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)  
 [Crear prototipos en código administrado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Llamar a una función DLL](../../../docs/framework/interop/calling-a-dll-function.md)
