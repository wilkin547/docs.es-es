---
title: /sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 876922385124db3e8db12c93c75194da83d2526c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sdkpath"></a><span data-ttu-id="d83ec-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="d83ec-102">/sdkpath</span></span>
<span data-ttu-id="d83ec-103">Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="d83ec-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d83ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d83ec-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="d83ec-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d83ec-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="d83ec-106">El directorio que contiene las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll a utilizar para la compilación.</span><span class="sxs-lookup"><span data-stu-id="d83ec-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="d83ec-107">Esta ruta de acceso no se comprueba hasta que se cargue.</span><span class="sxs-lookup"><span data-stu-id="d83ec-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="d83ec-108">Escriba el nombre de directorio entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="d83ec-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d83ec-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d83ec-109">Remarks</span></span>  
 <span data-ttu-id="d83ec-110">Esta opción indica el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador que cargue los archivos Mscorlib.dll y Microsoft.VisualBasic.dll desde una ubicación no predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d83ec-110">This option tells the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="d83ec-111">El `/sdkpath` opción se ha diseñado para utilizarse con [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="d83ec-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="d83ec-112">El [!INCLUDE[Compact](~/includes/compact-md.md)] utiliza diferentes versiones de estas bibliotecas de compatibilidad para evitar el uso de tipos y características del lenguaje no se encuentran en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d83ec-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d83ec-113">El `/sdkpath` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d83ec-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="d83ec-114">El `/sdkpath` opción se establece cuando un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se carga el proyecto de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d83ec-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="d83ec-115">Puede especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic mediante el uso de la `/vbruntime` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="d83ec-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="d83ec-116">Para obtener más información, consulte [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="d83ec-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d83ec-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d83ec-117">Example</span></span>  
 <span data-ttu-id="d83ec-118">El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utiliza las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminado de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="d83ec-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="d83ec-119">Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d83ec-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d83ec-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d83ec-120">See Also</span></span>  
 [<span data-ttu-id="d83ec-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d83ec-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d83ec-122">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d83ec-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d83ec-123">/netcf</span><span class="sxs-lookup"><span data-stu-id="d83ec-123">/netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="d83ec-124">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="d83ec-124">/vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
