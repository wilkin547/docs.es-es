---
description: Mas información sobre -win32icon
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 32a46771012708a42beb5450d28daf2fbab3f1c0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433554"
---
# <a name="-win32icon"></a><span data-ttu-id="fe6fe-103">-win32icon</span><span class="sxs-lookup"><span data-stu-id="fe6fe-103">-win32icon</span></span>

<span data-ttu-id="fe6fe-104">Inserta un archivo .ico en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-104">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="fe6fe-105">Este archivo .ico representa el archivo de salida en el **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-105">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe6fe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe6fe-106">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="fe6fe-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fe6fe-107">Arguments</span></span>  
  
|<span data-ttu-id="fe6fe-108">Término</span><span class="sxs-lookup"><span data-stu-id="fe6fe-108">Term</span></span>|<span data-ttu-id="fe6fe-109">Definición</span><span class="sxs-lookup"><span data-stu-id="fe6fe-109">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="fe6fe-110">El archivo .ico que se va a agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-110">The .ico file to add to your output file.</span></span> <span data-ttu-id="fe6fe-111">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="fe6fe-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe6fe-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe6fe-112">Remarks</span></span>  

 <span data-ttu-id="fe6fe-113">Puede crear un archivo .ico con el Compilador de recursos (RC) de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-113">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="fe6fe-114">El compilador de recursos se invoca al compilar un programa de Visual C++ y se crea un archivo .ico a partir del archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-114">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="fe6fe-115">Las opciones `-win32icon` y `-win32resource` son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-115">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="fe6fe-116">Vea [-linkresource (Visual Basic)](linkresource.md) para hacer referencia a un archivo de recursos de .NET Framework, o bien [-resource (Visual Basic)](resource.md) para adjuntar un archivo de recursos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-116">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="fe6fe-117">Vea [-win32resource](win32resource.md) para importar un archivo .res.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-117">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="fe6fe-118">Para establecer -win32icon en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fe6fe-118">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="fe6fe-119">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fe6fe-120">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="fe6fe-121">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="fe6fe-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="fe6fe-122">3.  Modifique el valor en el cuadro **Icono**.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fe6fe-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe6fe-123">Example</span></span>  

 <span data-ttu-id="fe6fe-124">El código siguiente compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe6fe-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6fe-125">See also</span></span>

- [<span data-ttu-id="fe6fe-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe6fe-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fe6fe-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe6fe-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
