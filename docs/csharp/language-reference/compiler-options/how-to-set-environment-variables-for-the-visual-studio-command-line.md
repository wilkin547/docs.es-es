---
title: 'Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio'
ms.date: 09/29/2017
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
ms.openlocfilehash: 77375e428fe0563c0b533ca97abd21070e850682
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43466743"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="cd1f3-102">Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cd1f3-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="cd1f3-103">El archivo VsDevCmd.bat establece las variables de entorno apropiadas para habilitar compilaciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="cd1f3-104">Para obtener más información sobre VsDevCmd.bat, vea el [artículo Q248802 de Knowledge Base](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span><span class="sxs-lookup"><span data-stu-id="cd1f3-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span></span>  

> [!NOTE]
> <span data-ttu-id="cd1f3-105">El archivo VsDevCmd.bat es un nuevo archivo que se proporciona con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="cd1f3-106">Visual Studio 2015 y las versiones anteriores usaban VSVARS32.bat para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="cd1f3-107">Este archivo se almacena en \Archivos de programa\Microsoft Visual Studio\\*Versión*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio\\*Versión*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="cd1f3-108">Si se instala la versión actual de Visual Studio en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar los archivos VsDevCmd.bat y VSVARS32.BAT de versiones diferentes en la misma ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="cd1f3-109">En su lugar, debe ejecutar el comando para cada versión en su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="cd1f3-110">Para ejecutar VsDevCmd.BAT:</span><span class="sxs-lookup"><span data-stu-id="cd1f3-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="cd1f3-111">En el menú **Inicio**, abra **Símbolo del sistema para desarrolladores de VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="cd1f3-112">Se encuentra en la carpeta **Visual Studio 2017**.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="cd1f3-113">Cambie al subdirectorio \Archivos de programa\Microsoft Visual Studio\\*Versión*\\*Oferta*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio\\*Versión*\\*Oferta*\Common7\Tools de la instalación.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="cd1f3-114">(*Versión* es *2017* para la versión actual.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="cd1f3-115">*Oferta* es una de las opciones siguientes: *Enterprise*, *Professional* o *Community*.)</span><span class="sxs-lookup"><span data-stu-id="cd1f3-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="cd1f3-116">Ejecute VsDevCmd.bat escribiendo **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="cd1f3-117">VsDevCmd.bat puede ser diferente en equipos distintos.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="cd1f3-118">No debe reemplazar un archivo VsDevCmd.bat dañado o inexistente por el archivo VsDevCmd.bat de otro equipo.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="cd1f3-119">En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.</span><span class="sxs-lookup"><span data-stu-id="cd1f3-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1f3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd1f3-120">See Also</span></span>  

- [<span data-ttu-id="cd1f3-121">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="cd1f3-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
