---
description: Establecimiento de variables de entorno para la línea de comandos de Visual Studio
title: Establecimiento de variables de entorno para la línea de comandos de Visual Studio
ms.date: 12/20/2019
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: b985c85e2fddce459ed68b3d07ba7d54a8b2d0a7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125610"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Establecimiento de variables de entorno para la línea de comandos de Visual Studio

El archivo VsDevCmd.bat establece las variables de entorno apropiadas para habilitar compilaciones desde la línea de comandos.

> [!NOTE]
> Visual Studio 2015 y versiones anteriores usaban VSVARS32.bat, no VsDevCmd.bat, para el mismo propósito. Este archivo se almacena en \Archivos de programa\Microsoft Visual Studio\\*Versión*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio\\*Versión*\Common7\Tools.

Si se instala la versión actual de Visual Studio en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar los archivos VsDevCmd.bat y VSVARS32.BAT de versiones diferentes en la misma ventana del símbolo del sistema. En su lugar, debe ejecutar el comando para cada versión en su propia ventana.

### <a name="to-run-vsdevcmdbat"></a>Para ejecutar VsDevCmd.BAT:

1. En el menú **Inicio**, abra el **símbolo del sistema para desarrolladores de VS 2019**.  Se encuentra en la carpeta **Visual Studio 2019**.

2. Cambie al subdirectorio \Archivos de programa\Microsoft Visual Studio\\*Versión*\\*Oferta*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio\\*Versión*\\*Oferta*\Common7\Tools de la instalación.  (*Versión* es *2019* para la versión actual. *Oferta* es una de las opciones siguientes: *Enterprise*, *Professional* o *Community*.)

3. Ejecute VsDevCmd.bat escribiendo **VsDevCmd**.

    > [!CAUTION]
    > VsDevCmd.bat puede ser diferente en equipos distintos. No debe reemplazar un archivo VsDevCmd.bat dañado o inexistente por el archivo VsDevCmd.bat de otro equipo. En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.

### <a name="available-options-for-vsdevcmdbat"></a>Opciones disponibles para VsDevCmd.BAT

Para ver las opciones disponibles para VsDevCmd.BAT, ejecute el comando con la opción `-help`:

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a>Vea también

- [Compilar la línea de comandos con csc.exe](./command-line-building-with-csc-exe.md)
