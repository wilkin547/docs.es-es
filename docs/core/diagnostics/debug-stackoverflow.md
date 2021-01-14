---
title: Depuración de errores de StackOverflow
description: Obtenga información sobre cómo diagnosticar excepciones de StackOverflow.
ms.topic: tutorial
ms.date: 12/22/2020
ms.openlocfilehash: 92edf854ddcc2e778949d74eff1370cf27db25b4
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "97764934"
---
# <a name="debugging-stackoverflow-errors"></a>Depuración de errores de StackOverflow

Se produce una excepción <xref:System.StackOverflowException> cuando la pila de ejecución se desborda debido a que contiene demasiadas llamadas a métodos anidadas.  

Por ejemplo, supongamos que tiene la siguiente aplicación:

````
using System;

namespace temp
{
    class Program
    {
        static void Main(string[] args)
        {
            Main(args); // oops this recursion won't stop
        }
    }
}
````

El método Main se llamará a sí mismo continuamente hasta que no haya más espacio de pila.  Cuando ya no haya más espacio de pila, no se podrá continuar con la ejecución y, por tanto, se producirá una excepción <xref:System.StackOverflowException>.  

````
> dotnet run
Stack overflow.
````

> [!NOTE]
> En .NET 5 y versiones posteriores, la pila de llamadas se envía a la consola.

> [!NOTE]
> En este artículo se describe cómo depurar un desbordamiento de pila con LLDB. Si usa Windows, se recomienda depurar la aplicación con [Visual Studio](/visualstudio/debugger/what-is-debugging) o [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging).  

## <a name="example"></a>Ejemplo

1. Ejecute la aplicación con la configuración para recopilar un volcado de memoria durante un bloqueo.

    ````
    > export COMPlus_DbgEnableMiniDump=1
    > dotnet run
    Stack overflow.
    Writing minidump with heap to file /tmp/coredump.6412
    Written 58191872 bytes (14207 pages) to core file
    ````

2. Instale la extensión SOS mediante [dotnet-sos](dotnet-sos.md).

    ````
    dotnet-sos install
    ````

3. Depure el volcado de memoria en LLDB para ver la pila con errores.

    ````
    lldb --core /temp/coredump.6412
    (lldb) bt
    ...
        frame #261930: 0x00007f59b40900cc
        frame #261931: 0x00007f59b40900cc
        frame #261932: 0x00007f59b40900cc
        frame #261933: 0x00007f59b40900cc
        frame #261934: 0x00007f59b40900cc
        frame #261935: 0x00007f5a2d4a080f libcoreclr.so`CallDescrWorkerInternal at unixasmmacrosamd64.inc:867
        frame #261936: 0x00007f5a2d3cc4c3 libcoreclr.so`MethodDescCallSite::CallTargetWorker(unsigned long const*, unsigned long*, int) at callhelpers.cpp:70
        frame #261937: 0x00007f5a2d3cc468 libcoreclr.so`MethodDescCallSite::CallTargetWorker(this=<unavailable>, pArguments=0x00007ffe8222e7b0, pReturnValue=0x0000000000000000, cbReturnValue=0) at callhelpers.cpp:604
        frame #261938: 0x00007f5a2d4b6182 libcoreclr.so`RunMain(MethodDesc*, short, int*, PtrArray**) [inlined] MethodDescCallSite::Call(this=<unavailable>, pArguments=<unavailable>) at callhelpers.h:468
    ...
    ````

4. El marco superior `0x00007f59b40900cc` se repite varias veces. Use el comando [SOS](sos-debugging-extension.md) `ip2md` para averiguar qué método se encuentra en la dirección `0x00007f59b40900cc`.

    ````
    (lldb) ip2md 0x00007f59b40900cc
    MethodDesc:   00007f59b413ffa8
    Method Name:          temp.Program.Main(System.String[])
    Class:                00007f59b4181d40
    MethodTable:          00007f59b4190020
    mdToken:              0000000006000001
    Module:               00007f59b413dbf8
    IsJitted:             yes
    Current CodeAddr:     00007f59b40900a0
    Version History:
      ILCodeVersion:      0000000000000000
      ReJIT ID:           0
      IL Addr:            0000000000000000
         CodeAddr:           00007f59b40900a0  (MinOptJitted)
         NativeCodeVersion:  0000000000000000
    Source file:  /temp/Program.cs @ 9
    ````

5. Vaya al método temp.Program.Main(System.String[]) indicado y al origen "/temp/Program.cs @ 9" para tratar de averiguar qué hizo mal. Si todavía no lo tiene claro, puede agregar funciones de registro en esa área del código.

## <a name="see-also"></a>Consulte también

* [Una introducción a los volcados de memoria en .NET](dumps.md)
* [Depuración de volcados de memoria de Linux](debug-linux-dumps.md)
* [Extensión de depuración de SOS para .NET](sos-debugging-extension.md)
