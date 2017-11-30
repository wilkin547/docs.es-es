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
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="95709-102">Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95709-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="95709-103">El archivo VsDevCmd.bat establece las variables de entorno apropiadas para habilitar las compilaciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="95709-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="95709-104">Para obtener más información sobre VsDevCmd.bat, consulte [artículo Q248802 de Knowledge Base](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="95709-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  

> [!NOTE]
> <span data-ttu-id="95709-105">El archivo VsDevCmd.bat es un nuevo archivo que se entregan con Visual Studio de 2017.</span><span class="sxs-lookup"><span data-stu-id="95709-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="95709-106">Visual Studio 2015 y versiones anteriores utilizan VSVARS32.bat para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="95709-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="95709-107">Este archivo se almacena en \Program Visual Studio\\*versión*\Common7\Tools o archivos de programa (x86) \Microsoft Visual Studio\\*versión*\Common7\Tools.</span><span class="sxs-lookup"><span data-stu-id="95709-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="95709-108">Si la versión actual de Visual Studio está instalada en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar VsDevCmd.bat y VSVARS32. BAT de versiones diferentes en la misma ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="95709-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="95709-109">En su lugar, debe ejecutar el comando para cada versión en su propia ventana.</span><span class="sxs-lookup"><span data-stu-id="95709-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="95709-110">Para ejecutar VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="95709-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="95709-111">Desde el **iniciar** menú, abra el **símbolo del sistema para desarrolladores de VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="95709-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="95709-112">Se encuentra en la **2017 de Visual Studio** carpeta.</span><span class="sxs-lookup"><span data-stu-id="95709-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="95709-113">Cambie a Visual Studio \Program\\*versión*\\*oferta*\Common7\Tools o \Program archivos (x86) \Microsoft Visual Studio\\ *Versión*\\*oferta*subdirectorio \Common7\Tools de la instalación.</span><span class="sxs-lookup"><span data-stu-id="95709-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="95709-114">(*Versión* es *2017* para la versión actual.</span><span class="sxs-lookup"><span data-stu-id="95709-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="95709-115">*Oferta* es uno de los *Enterprise*, *Professional* o *Comunidad*.)</span><span class="sxs-lookup"><span data-stu-id="95709-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="95709-116">Ejecutar VsDevCmd.bat escribiendo **VsDevCmd**.</span><span class="sxs-lookup"><span data-stu-id="95709-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="95709-117">VsDevCmd.bat puede variar de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="95709-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="95709-118">No reemplaza un archivo de VsDevCmd.bat dañado o que faltan con un VsDevCmd.bat desde otro equipo.</span><span class="sxs-lookup"><span data-stu-id="95709-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="95709-119">En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.</span><span class="sxs-lookup"><span data-stu-id="95709-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95709-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="95709-120">See Also</span></span>  
 [<span data-ttu-id="95709-121">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="95709-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
