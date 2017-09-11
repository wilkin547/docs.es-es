---
title: "Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
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
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 569683169c6d7ae50c33ed06d3b365a663f16715
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="e1e54-102">Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e1e54-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>
<span data-ttu-id="e1e54-103">El archivo vsvars32.bat establece las variables de entorno apropiadas para habilitar compilaciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e1e54-103">The vsvars32.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="e1e54-104">Para obtener más información sobre vsvars32.bat, vea el [artículo Q248802 de Knowledge Base](http://go.microsoft.com/fwlink/?LinkId=225042).</span><span class="sxs-lookup"><span data-stu-id="e1e54-104">For more information about vsvars32.bat, see [Knowledge Base article Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).</span></span>  
  
 <span data-ttu-id="e1e54-105">Si se instala la versión actual de Visual Studio en un equipo que también tiene una versión anterior de Visual Studio, no se deben ejecutar los archivos vsvars32.bat o vcvars32.bat de versiones diferentes en la misma ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e1e54-105">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run vsvars32.bat or vcvars32.bat from different versions in the same Command Prompt window.</span></span>  
  
### <a name="to-run-vsvars32bat"></a><span data-ttu-id="e1e54-106">Para ejecutar VSVARS32.BAT</span><span class="sxs-lookup"><span data-stu-id="e1e54-106">To run VSVARS32.BAT</span></span>  
  
1.  <span data-ttu-id="e1e54-107">En el menú **Inicio**, abra el **Símbolo del sistema para desarrolladores de VS2012**.</span><span class="sxs-lookup"><span data-stu-id="e1e54-107">From the **Start** menu, open the **Developer Command Prompt for VS2012**.</span></span>  
  
2.  <span data-ttu-id="e1e54-108">Cambie al subdirectorio Archivos de programa\Microsoft Visual Studio *Version*\Common7\Tools o Archivos de programa (x86)\Microsoft Visual Studio *Version*\Common7\Tools de la instalación.</span><span class="sxs-lookup"><span data-stu-id="e1e54-108">Change to the Program Files\Microsoft Visual Studio *Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools subdirectory of your installation.</span></span>  
  
3.  <span data-ttu-id="e1e54-109">Escriba **VSVARS32** para ejecutar VSVARS32.bat.</span><span class="sxs-lookup"><span data-stu-id="e1e54-109">Run VSVARS32.bat by typing **VSVARS32**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e1e54-110">VSVARS32.bat puede ser diferente en equipos distintos.</span><span class="sxs-lookup"><span data-stu-id="e1e54-110">VSVARS32.bat can vary from computer to computer.</span></span> <span data-ttu-id="e1e54-111">No debe reemplazar un archivo VSVARS32.bat dañado o inexistente por el archivo VSVARS32.bat de otro equipo.</span><span class="sxs-lookup"><span data-stu-id="e1e54-111">Do not replace a missing or damaged VSVARS32.bat file with a VSVARS32.bat from another computer.</span></span> <span data-ttu-id="e1e54-112">En su lugar, vuelva a ejecutar el programa de instalación para reemplazar el archivo que falta.</span><span class="sxs-lookup"><span data-stu-id="e1e54-112">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e54-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1e54-113">See Also</span></span>  
 [<span data-ttu-id="e1e54-114">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="e1e54-114">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

