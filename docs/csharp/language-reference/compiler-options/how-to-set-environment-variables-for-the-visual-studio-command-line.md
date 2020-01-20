---
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
ms.openlocfilehash: 99e2a837877494dd4c7e0106047bce3cc39a9282
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342362"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="b0d44-102">Establecimiento de variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0d44-102">How to set environment variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="b0d44-103">El archivo VsDevCmd.bat establece las variables de entorno apropiadas para habilitar compilaciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b0d44-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="b0d44-104">Visual Studio 2015 y versiones anteriores usaban VSVARS32.bat, no VsDevCmd.bat, para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="b0d44-104">Visual Studio 2015 and earlier versions used VSVARS32.bat, not VsDevCmd.bat for the same purpose.</span></span> <span data-ttu-id="b0d44-105">Este archivo se almacena en \Archivos de programa\Microsoft Visual Studio\\*Versión*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio\\*Versión*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="b0d44-105">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="b0d44-106">Si se instala la versión actual de Visual Studio en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar los archivos VsDevCmd.bat y VSVARS32.BAT de versiones diferentes en la misma ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b0d44-106">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="b0d44-107">En su lugar, debe ejecutar el comando para cada versión en su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="b0d44-107">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="b0d44-108">Para ejecutar VsDevCmd.BAT:</span><span class="sxs-lookup"><span data-stu-id="b0d44-108">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="b0d44-109">En el menú **Inicio**, abra el **símbolo del sistema para desarrolladores de VS 2019**.</span><span class="sxs-lookup"><span data-stu-id="b0d44-109">From the **Start** menu, open the **Developer Command Prompt for VS 2019**.</span></span>  <span data-ttu-id="b0d44-110">Se encuentra en la carpeta **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="b0d44-110">It's in the **Visual Studio 2019** folder.</span></span>

2. <span data-ttu-id="b0d44-111">Cambie al subdirectorio \Archivos de programa\Microsoft Visual Studio\\*Versión*\\*Oferta*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio\\*Versión*\\*Oferta*\Common7\Tools de la instalación.</span><span class="sxs-lookup"><span data-stu-id="b0d44-111">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="b0d44-112">(*Versión* es *2019* para la versión actual.</span><span class="sxs-lookup"><span data-stu-id="b0d44-112">(*Version* is *2019* for the current version.</span></span> <span data-ttu-id="b0d44-113">*Oferta* es una de las opciones siguientes: *Enterprise*, *Professional* o *Community*.)</span><span class="sxs-lookup"><span data-stu-id="b0d44-113">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="b0d44-114">Ejecute VsDevCmd.bat escribiendo **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="b0d44-114">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b0d44-115">VsDevCmd.bat puede ser diferente en equipos distintos.</span><span class="sxs-lookup"><span data-stu-id="b0d44-115">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="b0d44-116">No debe reemplazar un archivo VsDevCmd.bat dañado o inexistente por el archivo VsDevCmd.bat de otro equipo.</span><span class="sxs-lookup"><span data-stu-id="b0d44-116">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="b0d44-117">En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.</span><span class="sxs-lookup"><span data-stu-id="b0d44-117">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="b0d44-118">Opciones disponibles para VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="b0d44-118">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="b0d44-119">Para ver las opciones disponibles para VsDevCmd.BAT, ejecute el comando con la opción `-help`:</span><span class="sxs-lookup"><span data-stu-id="b0d44-119">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="b0d44-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d44-120">See also</span></span>

- [<span data-ttu-id="b0d44-121">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="b0d44-121">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
