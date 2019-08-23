---
title: Funciones externas
description: Obtenga información sobre F# la compatibilidad de lenguajes para llamar a funciones en código nativo.
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968726"
---
# <a name="external-functions"></a>Funciones externas

En este tema F# se describe la compatibilidad con lenguajes para llamar a funciones en código nativo.

## <a name="syntax"></a>Sintaxis

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *arguments* representa los `System.Runtime.InteropServices.DllImportAttribute` argumentos que se proporcionan al atributo. El primer argumento es una cadena que representa el nombre del archivo DLL que contiene esta función, sin la extensión. dll. Se pueden proporcionar argumentos adicionales para cualquiera de las propiedades públicas de la `System.Runtime.InteropServices.DllImportAttribute` clase, como la Convención de llamada.

Suponga que tiene un archivo C++ dll nativo que contiene la siguiente función exportada.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Puede llamar a esta función desde F# mediante el código siguiente.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

La interoperabilidad con código nativo se conoce como invocación de *plataforma* y es una característica de CLR. Para más información, consulte [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado) La información de esa sección es aplicable a F#.

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
