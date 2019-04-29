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
ms.openlocfilehash: 9351e9f6bcb7660dac2c49667ca8db6d578eff7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774769"
---
# <a name="-win32resource"></a><span data-ttu-id="98aa2-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="98aa2-102">-win32resource</span></span>
<span data-ttu-id="98aa2-103">Inserta un archivo de recursos de Win32 en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="98aa2-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98aa2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98aa2-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="98aa2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="98aa2-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="98aa2-106">El nombre del archivo de recursos para agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="98aa2-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="98aa2-107">Ponga el nombre de archivo entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="98aa2-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98aa2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98aa2-108">Remarks</span></span>  
 <span data-ttu-id="98aa2-109">Puede crear un archivo de recursos de Win32 con el compilador de recursos de Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="98aa2-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="98aa2-110">Un recurso de Win32 puede contener la versión o información de mapa de bits (icono) que ayuda a identificar la aplicación en **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="98aa2-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="98aa2-111">Si no especifica `-win32resource`, el compilador genera información de versión basada en la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98aa2-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="98aa2-112">El `-win32resource` y `-win32icon` opciones son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="98aa2-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="98aa2-113">Consulte [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos, o [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="98aa2-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98aa2-114">El `-win32resource` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="98aa2-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98aa2-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98aa2-115">Example</span></span>  
 <span data-ttu-id="98aa2-116">El siguiente código compila `In.vb` y adjunta un archivo de recursos de Win32, `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="98aa2-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="98aa2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="98aa2-117">See also</span></span>

- [<span data-ttu-id="98aa2-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98aa2-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="98aa2-119">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="98aa2-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
