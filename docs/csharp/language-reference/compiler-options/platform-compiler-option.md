---
description: -platform (Opciones del compilador de C#)
title: -platform (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 3fdb030dfc141b011f5faa827a4e4bb45ae38d19
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466019"
---
# <a name="-platform-c-compiler-options"></a>-platform (Opciones del compilador de C#)

Especifica qué versión de Common Language Runtime (CLR) puede ejecutar el ensamblado.

## <a name="syntax"></a>Sintaxis

```console
-platform:string
```

## <a name="parameters"></a>Parámetros

`string` \
anycpu (valor predeterminado), anycpu32bitpreferred, ARM, x64, x86 o Itanium.

## <a name="remarks"></a>Observaciones

- **anycpu** (valor predeterminado) compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma. La aplicación se ejecuta como un proceso de 64 bits siempre que sea posible y recurre a 32 bits solo cuando el modo está disponible.

- **anycpu32bitpreferred** compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma. La aplicación se ejecuta en modo de 32 bits en sistemas que admiten aplicaciones de 64 y 32 bits. Solo puede especificar esta opción para los proyectos que tienen como destino .NET Framework 4.5 o versiones posteriores.

- **ARM** compila el ensamblado de forma que pueda ejecutarse en un equipo que tenga un procesador Advanced RISC Machine (ARM).

- **ARM64** compila el ensamblado que se va a ejecutar mediante el CLR de 64 bits en un equipo que tiene un procesador Advanced RISC Machine (ARM) que admite el conjunto de instrucciones A64.

- **x64** compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.

- **x86** compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.

- **Itanium** compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.

En un sistema operativo de Windows de 64 bits:

- Los ensamblados compilados con **-platform:x86** se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.

- Un archivo DLL compilado con **-platform:anycpu** se ejecuta en el mismo CLR que el proceso en el que se ha cargado.

- Los archivos ejecutables que se compilan con **-platform:anycpu** se ejecutan en el CLR de 64 bits.

- Los archivos ejecutables compilados con **-platform:anycpu32bitpreferred** se ejecutan en el CLR de 32 bits.

El valor **anycpu32bitpreferred** solo es válido para archivos ejecutables (.EXE) y requiere .NET Framework 4.5 o una versión posterior.

Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en un sistema operativo Windows de 64 bits, consulte [Aplicaciones de 64 bits](../../../framework/64-bit-apps.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra la página **Propiedades** del proyecto.

2. Haga clic en la página de propiedades de **Compilar**.

3. Modifique la propiedad **Destino de la plataforma** y, para los proyectos que tienen como destino .NET Framework 4.5 o una versión posterior, active o desactive la casilla **Preferencia de 32 bits**.

> [!NOTE]
> `-platform` no está disponible en el entorno de desarrollo de Visual C# Express.

Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se muestra cómo usar la opción **-platform** para especificar que la aplicación se debe ejecutar en el CLR de 64 bits en un sistema operativo Windows de 64 bits.

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
