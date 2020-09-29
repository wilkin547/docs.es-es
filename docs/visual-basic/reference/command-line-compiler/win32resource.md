---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: d146f5967058b05795026cd7726ed5eda7ba3153
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095413"
---
# <a name="-win32resource"></a><span data-ttu-id="c91c7-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="c91c7-102">-win32resource</span></span>

<span data-ttu-id="c91c7-103">Inserta un archivo recursos de Win32 en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c91c7-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c91c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c91c7-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c91c7-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c91c7-105">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="c91c7-106">Nombre del archivo de recursos que se va a agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c91c7-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="c91c7-107">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="c91c7-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c91c7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c91c7-108">Remarks</span></span>  

 <span data-ttu-id="c91c7-109">Puede crear un archivo de recursos de Win32 con el compilador de recursos de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="c91c7-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="c91c7-110">Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayuda a identificar la aplicación en el **Explorador de Windows**.</span><span class="sxs-lookup"><span data-stu-id="c91c7-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="c91c7-111">Si no se especifica `-win32resource`, el compilador generará información de versión basada en la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c91c7-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="c91c7-112">Las opciones `-win32resource` y `-win32icon` son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="c91c7-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="c91c7-113">Vea [-linkresource (Visual Basic)](linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o bien [-resource (Visual Basic)](resource.md) para adjuntar un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c91c7-113">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c91c7-114">La opción `-win32resource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c91c7-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c91c7-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c91c7-115">Example</span></span>  

 <span data-ttu-id="c91c7-116">El siguiente código compila `In.vb` y adjunta un archivo de recursos de Win32, `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="c91c7-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c91c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c91c7-117">See also</span></span>

- [<span data-ttu-id="c91c7-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c91c7-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c91c7-119">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c91c7-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
