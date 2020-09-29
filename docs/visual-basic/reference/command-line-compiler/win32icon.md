---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: c6d5e054063592db5777a76fe19da79337ed5034
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084962"
---
# <a name="-win32icon"></a><span data-ttu-id="24f83-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="24f83-102">-win32icon</span></span>

<span data-ttu-id="24f83-103">Inserta un archivo .ico en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="24f83-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="24f83-104">Este archivo .ico representa el archivo de salida en el **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="24f83-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f83-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24f83-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="24f83-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="24f83-106">Arguments</span></span>  
  
|<span data-ttu-id="24f83-107">Término</span><span class="sxs-lookup"><span data-stu-id="24f83-107">Term</span></span>|<span data-ttu-id="24f83-108">Definición</span><span class="sxs-lookup"><span data-stu-id="24f83-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="24f83-109">El archivo .ico que se va a agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="24f83-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="24f83-110">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="24f83-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24f83-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24f83-111">Remarks</span></span>  

 <span data-ttu-id="24f83-112">Puede crear un archivo .ico con el Compilador de recursos (RC) de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="24f83-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="24f83-113">El compilador de recursos se invoca al compilar un programa de Visual C++ y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="24f83-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="24f83-114">Las opciones `-win32icon` y `-win32resource` son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="24f83-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="24f83-115">Vea [-linkresource (Visual Basic)](linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o bien [-resource (Visual Basic)](resource.md) para adjuntar un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24f83-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="24f83-116">Vea [-win32resource](win32resource.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="24f83-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="24f83-117">Para establecer -win32icon en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24f83-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="24f83-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="24f83-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="24f83-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="24f83-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="24f83-120">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="24f83-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="24f83-121">3.  Modifique el valor en el cuadro **Icono**.</span><span class="sxs-lookup"><span data-stu-id="24f83-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="24f83-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24f83-122">Example</span></span>  

 <span data-ttu-id="24f83-123">El código siguiente compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="24f83-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="24f83-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="24f83-124">See also</span></span>

- [<span data-ttu-id="24f83-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24f83-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="24f83-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="24f83-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
