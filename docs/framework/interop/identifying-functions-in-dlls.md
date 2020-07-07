---
title: Identificar funciones en archivos DLL
description: Identifique funciones en archivos DLL. La identidad de una función DLL se compone de un nombre de función o un ordinal, y el nombre del archivo DLL en el que se puede encontrar la implementación.
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
ms.openlocfilehash: 054d1351a9ee6adab17117c9f423aa26d0d9ed59
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622736"
---
# <a name="identifying-functions-in-dlls"></a>Identificar funciones en archivos DLL
La identidad de una función DLL consta de los siguientes elementos:  
  
- Nombre de la función u ordinal  
  
- Nombre del archivo DLL en el que se puede encontrar la implementación  
  
 Por ejemplo, si se especifica la función **MessageBox** en el archivo User32.dll se identifica la función (**MessageBox**) y su ubicación (User32.dll, User32 o user32). La interfaz de programación de aplicaciones de Microsoft Windows (API de Windows) puede contener dos versiones de cada función que controla caracteres y cadenas: una versión ANSI de caracteres de un byte y una versión Unicode de caracteres de dos bytes. Si no se especifica, el juego de caracteres (representado por el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>) es ANSI de manera predeterminada. Algunas funciones pueden tener más de dos versiones.  
  
 **MessageBoxA** es el punto de entrada ANSI para la función **MessageBox**; **MessageBoxW** es la versión de Unicode. Puede enumerar los nombres de función de un archivo DLL específico, como user32.dll, mediante la ejecución de una variedad de herramientas de línea de comandos. Por ejemplo, puede usar `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` para obtener los nombres de función.  
  
 Puede cambiar el nombre de una función no administrada por el nombre que quiera dentro del código siempre que se asigne el nombre nuevo al punto de entrada original en el archivo DLL. Para obtener instrucciones sobre cómo cambiar el nombre de una función DLL no administrada en código fuente administrado, vea [Especificar un punto de entrada](specifying-an-entry-point.md).  
  
 La invocación de plataforma permite controlar una parte importante del sistema operativo mediante la llamada a las funciones de la API de Windows y otros archivos DLL. Además de la API de Windows, hay muchas otras API y archivos DLL disponibles a través de la invocación de plataforma.  
  
 En la tabla siguiente se describen varios archivos DLL que se usan habitualmente en la API de Windows.  
  
|Archivo DLL|Descripción del contenido|  
|---------|-----------------------------|  
|GDI32.dll|Funciones de Interfaz de dispositivo gráfico (GDI) para salida de dispositivos, como las de dibujo y administración de fuentes.|  
|Kernel32.dll|Funciones de bajo nivel del sistema operativo para la administración de memoria y el control de recursos.|  
|User32.dll|Funciones de administración de Windows para el control de mensajes, temporizadores, menús y comunicaciones.|  
  
 Para obtener la documentación completa sobre la API de Windows, vea el SDK de la plataforma. Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Vea también

- [Consumir funciones DLL no administradas](consuming-unmanaged-dll-functions.md)
- [Especificar un punto de entrada](specifying-an-entry-point.md)
- [Creación de una clase para contener funciones de archivos DLL](creating-a-class-to-hold-dll-functions.md)
- [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
- [Llamar a una función DLL](calling-a-dll-function.md)
