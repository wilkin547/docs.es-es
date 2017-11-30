---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65149c617220966bc3bb6897d757a71cd60167d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="e2cbb-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="e2cbb-102">/win32icon</span></span>
<span data-ttu-id="e2cbb-103">Inserta un archivo .ico en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="e2cbb-104">Este archivo .ico representa el archivo de salida en **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2cbb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2cbb-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2cbb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e2cbb-106">Arguments</span></span>  
  
|<span data-ttu-id="e2cbb-107">Término</span><span class="sxs-lookup"><span data-stu-id="e2cbb-107">Term</span></span>|<span data-ttu-id="e2cbb-108">Definición</span><span class="sxs-lookup"><span data-stu-id="e2cbb-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="e2cbb-109">El archivo .ico para agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="e2cbb-110">Ponga el nombre de archivo entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2cbb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2cbb-111">Remarks</span></span>  
 <span data-ttu-id="e2cbb-112">Puede crear un archivo .ico con el compilador de recursos de Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="e2cbb-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="e2cbb-113">El compilador de recursos se invoca cuando se compila un programa de Visual C++; se crea un archivo .ico en el archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="e2cbb-114">El `/win32icon` y `/win32resource` opciones son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="e2cbb-115">Vea [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="e2cbb-116">Vea [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) para importar un archivo. res.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="e2cbb-117">Para establecer /win32icon en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2cbb-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e2cbb-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e2cbb-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e2cbb-120">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="e2cbb-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="e2cbb-121">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="e2cbb-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="e2cbb-122">3.  Modifique el valor en el **icono** cuadro.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e2cbb-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2cbb-123">Example</span></span>  
 <span data-ttu-id="e2cbb-124">El siguiente código compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="e2cbb-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2cbb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2cbb-125">See Also</span></span>  
 [<span data-ttu-id="e2cbb-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2cbb-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e2cbb-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2cbb-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
