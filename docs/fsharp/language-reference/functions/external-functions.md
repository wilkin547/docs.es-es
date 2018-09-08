---
title: Funciones externas (F#)
description: 'Obtenga información sobre la compatibilidad del lenguaje F # para llamar a funciones en código nativo.'
ms.date: 05/16/2016
ms.openlocfilehash: db0d3362d867b07b333951f3380c6735ff471d5e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44181424"
---
# <a name="external-functions"></a>Funciones externas

Este tema describe la compatibilidad del lenguaje F # para llamar a funciones en código nativo.

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

Puede llamar a esta función de F # con el código siguiente.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilidad con código nativo se conoce como *de invocación de plataforma* y es una característica de CLR. Para más información, consulte [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado) La información de esa sección es aplicable a F #.

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
