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
ms.openlocfilehash: 2024ccadb06fdea0c24d9d304c2fe040f8cce1d5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814333"
---
# <a name="-sdkpath"></a><span data-ttu-id="00cb2-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="00cb2-102">-sdkpath</span></span>
<span data-ttu-id="00cb2-103">Especifica la ubicación de mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="00cb2-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00cb2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00cb2-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="00cb2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="00cb2-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="00cb2-106">El directorio que contiene las versiones de mscorlib.dll y Microsoft.VisualBasic.dll a utilizar para la compilación.</span><span class="sxs-lookup"><span data-stu-id="00cb2-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="00cb2-107">No se comprueba esta ruta de acceso hasta que se carga.</span><span class="sxs-lookup"><span data-stu-id="00cb2-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="00cb2-108">Escriba el nombre de directorio entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="00cb2-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00cb2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00cb2-109">Remarks</span></span>  
 <span data-ttu-id="00cb2-110">Esta opción indica al compilador de Visual Basic para cargar el archivo mscorlib.dll y Microsoft.VisualBasic.dll archivos desde una ubicación no predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00cb2-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="00cb2-111">El `-sdkpath` opción se ha diseñado para usarse con [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="00cb2-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="00cb2-112">El [!INCLUDE[Compact](~/includes/compact-md.md)] utiliza diferentes versiones de estas bibliotecas de compatibilidad para evitar el uso de tipos y características de lenguaje no se encuentran en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="00cb2-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cb2-113">El `-sdkpath` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="00cb2-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="00cb2-114">El `-sdkpath` opción se establece cuando se carga un proyecto de dispositivo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="00cb2-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="00cb2-115">Puede especificar que el compilador debe compilar sin referencia alguna a la biblioteca en tiempo de ejecución de Visual Basic utilizando la `-vbruntime` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="00cb2-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="00cb2-116">Para obtener más información, consulte [- vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="00cb2-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00cb2-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00cb2-117">Example</span></span>  
 <span data-ttu-id="00cb2-118">El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utilizando las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminada de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="00cb2-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="00cb2-119">Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00cb2-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="00cb2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="00cb2-120">See also</span></span>

- [<span data-ttu-id="00cb2-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00cb2-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="00cb2-122">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="00cb2-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="00cb2-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="00cb2-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="00cb2-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="00cb2-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
