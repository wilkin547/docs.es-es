---
title: Funciones externas (F#)
description: "Obtenga información sobre la compatibilidad de idioma de F # para llamar a funciones en código nativo."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a>Funciones externas

Este tema describe la compatibilidad de idioma de F # para llamar a funciones en código nativo.

## <a name="syntax"></a>Sintaxis

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *argumentos* representa los argumentos que se proporcionan para el `System.Runtime.InteropServices.DllImportAttribute` atributo. El primer argumento es una cadena que representa el nombre de la DLL que contiene esta función, sin la extensión. dll. Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.

Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Puede llamar a esta función de F # mediante el siguiente código.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR. Para más información, consulte [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx) (Interoperar con código no administrado) La información de esa sección es aplicable a F #.


## <a name="see-also"></a>Vea también

[Funciones](index.md)
