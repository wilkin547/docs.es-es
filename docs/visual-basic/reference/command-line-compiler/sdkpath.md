---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 18bf22861c1cbc3a37ef917b421491c2d01efba8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085118"
---
# <a name="-sdkpath"></a><span data-ttu-id="c9a3c-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="c9a3c-102">-sdkpath</span></span>

<span data-ttu-id="c9a3c-103">Especifica la ubicación de mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9a3c-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9a3c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c9a3c-105">Arguments</span></span>  

 `path`  
 <span data-ttu-id="c9a3c-106">Directorio que contiene las versiones de mscorlib.dll y Microsoft.VisualBasic.dll que se van a usar para la compilación.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="c9a3c-107">Esta ruta de acceso no se comprueba hasta que se carga.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="c9a3c-108">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="c9a3c-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9a3c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9a3c-109">Remarks</span></span>  

 <span data-ttu-id="c9a3c-110">Esta opción indica al compilador de Visual Basic que cargue los archivos mscorlib.dll y Microsoft.VisualBasic.dll desde una ubicación no predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="c9a3c-111">La opción `-sdkpath` se ha diseñado para usarse con [-netcf](netcf.md).</span><span class="sxs-lookup"><span data-stu-id="c9a3c-111">The `-sdkpath` option was designed to be used with [-netcf](netcf.md).</span></span> <span data-ttu-id="c9a3c-112">En .NET Compact Framework se usan otras versiones de estas bibliotecas de compatibilidad para evitar el uso de tipos y características del lenguaje que no se encuentran en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9a3c-113">La opción `-sdkpath` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="c9a3c-114">La opción `-sdkpath` se establece cuando se carga un proyecto de dispositivo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="c9a3c-115">Puede especificar que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic mediante la opción del compilador `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="c9a3c-116">Para obtener más información, vea [-vbruntime](vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="c9a3c-116">For more information, see [-vbruntime](vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9a3c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9a3c-117">Example</span></span>  

 <span data-ttu-id="c9a3c-118">El código siguiente compila `Myfile.vb` con .NET Compact Framework, mediante las versiones de mscorlib.dll y Microsoft.VisualBasic.dll que se encuentran en el directorio de instalación predeterminado de .NET Compact Framework en la unidad C.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="c9a3c-119">Normalmente, se usaría la versión más reciente de .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="c9a3c-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9a3c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9a3c-120">See also</span></span>

- [<span data-ttu-id="c9a3c-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9a3c-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c9a3c-122">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9a3c-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="c9a3c-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="c9a3c-123">-netcf</span></span>](netcf.md)
- [<span data-ttu-id="c9a3c-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="c9a3c-124">-vbruntime</span></span>](vbruntime.md)
