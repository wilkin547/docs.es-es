---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004633"
---
# <a name="-win32icon"></a><span data-ttu-id="70a88-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="70a88-102">-win32icon</span></span>
<span data-ttu-id="70a88-103">Inserta un archivo .ico en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="70a88-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="70a88-104">Este archivo .ico representa el archivo de salida en el **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="70a88-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70a88-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70a88-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="70a88-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="70a88-106">Arguments</span></span>  
  
|<span data-ttu-id="70a88-107">Término</span><span class="sxs-lookup"><span data-stu-id="70a88-107">Term</span></span>|<span data-ttu-id="70a88-108">Definición</span><span class="sxs-lookup"><span data-stu-id="70a88-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="70a88-109">El archivo .ico que se va a agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="70a88-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="70a88-110">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="70a88-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70a88-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70a88-111">Remarks</span></span>  
 <span data-ttu-id="70a88-112">Puede crear un archivo .ico con el Compilador de recursos (RC) de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="70a88-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="70a88-113">El compilador de recursos se invoca al compilar un programa de Visual C++ y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="70a88-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="70a88-114">Las opciones `-win32icon` y `-win32resource` son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="70a88-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="70a88-115">Vea [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o bien [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70a88-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="70a88-116">Vea [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="70a88-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="70a88-117">Para establecer -win32icon en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="70a88-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="70a88-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="70a88-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="70a88-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="70a88-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="70a88-120">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="70a88-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="70a88-121">3.  Modifique el valor en el cuadro **Icono**.</span><span class="sxs-lookup"><span data-stu-id="70a88-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="70a88-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70a88-122">Example</span></span>  
 <span data-ttu-id="70a88-123">El código siguiente compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="70a88-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="70a88-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="70a88-124">See also</span></span>

- [<span data-ttu-id="70a88-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70a88-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="70a88-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="70a88-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
