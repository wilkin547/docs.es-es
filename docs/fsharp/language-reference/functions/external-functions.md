---
title: Funciones externas
description: Obtenga información sobre la F# compatibilidad de lenguaje para llamar a funciones en código nativo.
ms.date: 05/16/2016
ms.openlocfilehash: 73e38d8942bfc8ddb3c51d126d7678e84903326b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642041"
---
# <a name="external-functions"></a>Funciones externas

Este tema se describe F# compatibilidad de lenguaje para llamar a funciones en código nativo.

## <a name="syntax"></a>Sintaxis

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *argumentos* representa los argumentos que se suministran a la `System.Runtime.InteropServices.DllImportAttribute` atributo. El primer argumento es una cadena que representa el nombre del archivo DLL que contiene esta función, sin la extensión. dll. Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` (clase), por ejemplo, la convención de llamada.

Suponga que tiene un archivo DLL de C++ que contiene la siguiente función exportada nativo.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Puede llamar a esta función desde F# con el código siguiente.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR. Para más información, consulte [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado) La información de esa sección es aplicable a F#.

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
