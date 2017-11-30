---
title: /out (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d98a9f3cadc42021c302915cfc5b058b41e11ec6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="out-visual-basic"></a><span data-ttu-id="78513-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78513-102">/out (Visual Basic)</span></span>
<span data-ttu-id="78513-103">Especifica el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="78513-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78513-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78513-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="78513-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="78513-105">Arguments</span></span>  
  
|<span data-ttu-id="78513-106">Término</span><span class="sxs-lookup"><span data-stu-id="78513-106">Term</span></span>|<span data-ttu-id="78513-107">Definición</span><span class="sxs-lookup"><span data-stu-id="78513-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="78513-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="78513-108">Required.</span></span> <span data-ttu-id="78513-109">Crea el nombre del archivo de salida del compilador.</span><span class="sxs-lookup"><span data-stu-id="78513-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="78513-110">Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="78513-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78513-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78513-111">Remarks</span></span>  
 <span data-ttu-id="78513-112">Especifique el nombre completo y la extensión de archivo que desea crear.</span><span class="sxs-lookup"><span data-stu-id="78513-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="78513-113">Si no lo hace, el archivo .exe adopta el nombre del archivo de código fuente que contiene el `Sub Main` procedimiento y el archivo .dll adopta el nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="78513-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="78513-114">Si especifica un nombre de archivo sin una extensión .exe o .dll, el compilador agrega automáticamente la extensión automáticamente, según el valor especificado para el `/target` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="78513-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="78513-115">Para establecer/out en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="78513-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="78513-116">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="78513-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="78513-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="78513-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="78513-118">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="78513-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="78513-119">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="78513-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="78513-120">3.  Modifique el valor en el **nombre de ensamblado** cuadro.</span><span class="sxs-lookup"><span data-stu-id="78513-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="78513-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78513-121">Example</span></span>  
 <span data-ttu-id="78513-122">El siguiente código compila `T2.vb` y crea el archivo de salida `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="78513-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="78513-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="78513-123">See Also</span></span>  
 [<span data-ttu-id="78513-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78513-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="78513-125">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78513-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="78513-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="78513-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
