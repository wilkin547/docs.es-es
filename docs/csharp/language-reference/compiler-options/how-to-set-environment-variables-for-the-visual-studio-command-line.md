---
title: "Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio"
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
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
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio

El archivo VsDevCmd.bat establece las variables de entorno apropiadas para habilitar las compilaciones de línea de comandos. Para obtener más información sobre VsDevCmd.bat, consulte [artículo Q248802 de Knowledge Base](http://go.microsoft.com/fwlink/?LinkId=225042).  

> [!NOTE]
> El archivo VsDevCmd.bat es un nuevo archivo que se entregan con Visual Studio de 2017. Visual Studio 2015 y versiones anteriores utilizan VSVARS32.bat para el mismo propósito. Este archivo se almacena en \Program Visual Studio\\*versión*\Common7\Tools o archivos de programa (x86) \Microsoft Visual Studio\\*versión*\Common7\Tools.
  
Si la versión actual de Visual Studio está instalada en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar VsDevCmd.bat y VSVARS32. BAT de versiones diferentes en la misma ventana del símbolo del sistema. En su lugar, debe ejecutar el comando para cada versión en su propia ventana.
  
### <a name="to-run-vsdevcmdbat"></a>Para ejecutar VsDevCmd.BAT  
  
1.  Desde el **iniciar** menú, abra el **símbolo del sistema para desarrolladores de VS 2017**.  Se encuentra en la **2017 de Visual Studio** carpeta.
  
2.  Cambie a Visual Studio \Program\\*versión*\\*oferta*\Common7\Tools o \Program archivos (x86) \Microsoft Visual Studio\\ *Versión*\\*oferta*subdirectorio \Common7\Tools de la instalación.  (*Versión* es *2017* para la versión actual. *Oferta* es uno de los *Enterprise*, *Professional* o *Comunidad*.)
  
3.  Ejecutar VsDevCmd.bat escribiendo **VsDevCmd**.  
  
    > [!CAUTION]
    >  VsDevCmd.bat puede variar de un equipo a otro. No reemplaza un archivo de VsDevCmd.bat dañado o que faltan con un VsDevCmd.bat desde otro equipo. En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.  
  
## <a name="see-also"></a>Vea también  
 [Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
