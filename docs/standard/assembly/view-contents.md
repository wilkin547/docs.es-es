---
title: Procedimiento para ver el contenido de un ensamblado
description: Puede usar el desensamblador de IL para ver los atributos de un ensamblado y las referencias a otros módulos y ensamblados.
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: be2311c601effbebd519e33b7a5e13d49f44bd05
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687502"
---
# <a name="how-to-view-assembly-contents"></a>Procedimiento para ver el contenido de un ensamblado

Se puede usar [Ildasm.exe (Desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) para ver la información del Lenguaje intermedio de Microsoft (MSIL) de un archivo. Si el archivo que se examina es un ensamblado, esta información puede incluir los atributos del ensamblado y referencias a otros módulos y ensamblados. Esta información puede ser útil para determinar si un archivo es un ensamblado o forma parte de uno y si el archivo tiene referencias a otros módulos o ensamblados.

Para mostrar el contenido de un ensamblado mediante *Ildasm.exe* , escriba **ildasm \<assembly name>** en un símbolo del sistema. Por ejemplo, el comando siguiente desensambla el ensamblado *Hello.exe*.

```cmd
ildasm Hello.exe
```

Para ver la información del manifiesto del ensamblado, haga doble clic en el icono **Manifiesto** en la ventana del desensamblador de MSIL.

## <a name="example"></a>Ejemplo

El ejemplo siguiente se inicia con un programa básico “Hola mundo”. Después de compilar el programa, use *Ildasm.exe* para desensamblar el ensamblado *Hello.exe* y ver el manifiesto del ensamblado.

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

Al ejecutar el comando *ildasm.exe* en el ensamblado *Hello.exe* y hacer doble clic en el icono **Manifiesto** en la ventana del desensamblador de MSIL, se produce lo siguiente:

```output
// Metadata version: v4.0.30319
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 4:0:0:0
}
.assembly Hello
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module Hello.exe
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x00600000
```

En la tabla siguiente se explica cada directiva del manifiesto del ensamblado *Hello.exe* usado en el ejemplo:

|Directiva|Descripción|
|---------------|-----------------|
|**.assembly extern \<assembly name>**|Especifica otro ensamblado que contiene elementos a los que hace referencia el módulo actual (en este ejemplo, `mscorlib`).|
|**.publickeytoken \<token>**|Especifica el token de la clave real del ensamblado al que se hace referencia.|
|**.ver \<version number>**|Especifica el número de versión del ensamblado al que se hace referencia.|
|**.assembly \<assembly name>**|Especifica el nombre del ensamblado.|
|**.hash algorithm \<int32 value>**|Especifica el algoritmo hash usado.|
|**.ver \<version number>**|Especifica el número de versión del ensamblado.|
|**.module \<file name>**|Especifica el nombre de los módulos que componen el ensamblado. En este ejemplo, el ensamblado consta de un único archivo.|
|**.subsystem \<value>**|Especifica el entorno de aplicación necesario para el programa. En este ejemplo, el valor 3 indica que este ejecutable se ejecuta desde una consola.|
|**.corflags**|De momento, un campo reservado de los metadatos.|

Un manifiesto de ensamblado puede contener varias directivas diferentes, según el contenido del ensamblado. Para obtener una lista completa de las directivas del manifiesto del ensamblado, vea la documentación de Ecma, especialmente "Partition II: Metadata Definition and Semantics (Partición II: definición y semántica de los metadatos)" y "Partition III: CIL Instruction Set (Partición III: conjunto de instrucciones CIL)”.

- [Estándares de ECMA C# y Common Language Infrastructure](../components.md#applicable-standards)
- [Estándar ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a>Vea también

- [Dominios de aplicación y ensamblados](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [Temas sobre dominios de aplicación y ensamblados](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [Ildasm.exe (Desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md)
