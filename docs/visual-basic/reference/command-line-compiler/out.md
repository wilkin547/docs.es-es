---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 234071d043b2649e2438ed20fe044fb89cdb9bf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655894"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="26fc6-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26fc6-102">-out (Visual Basic)</span></span>
<span data-ttu-id="26fc6-103">Especifica el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="26fc6-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26fc6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26fc6-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="26fc6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="26fc6-105">Arguments</span></span>  
  
|<span data-ttu-id="26fc6-106">Término</span><span class="sxs-lookup"><span data-stu-id="26fc6-106">Term</span></span>|<span data-ttu-id="26fc6-107">Definición</span><span class="sxs-lookup"><span data-stu-id="26fc6-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="26fc6-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="26fc6-108">Required.</span></span> <span data-ttu-id="26fc6-109">Crea el nombre del archivo de salida del compilador.</span><span class="sxs-lookup"><span data-stu-id="26fc6-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="26fc6-110">Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="26fc6-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26fc6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26fc6-111">Remarks</span></span>  
 <span data-ttu-id="26fc6-112">Especifique el nombre completo y la extensión de archivo que desea crear.</span><span class="sxs-lookup"><span data-stu-id="26fc6-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="26fc6-113">Si no lo hace, el archivo .exe adopta el nombre del archivo de código fuente que contiene el `Sub Main` procedimiento y el archivo .dll adopta el nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="26fc6-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="26fc6-114">Si especifica un nombre de archivo sin una extensión .exe o .dll, el compilador agrega automáticamente la extensión automáticamente, según el valor especificado para el `-target` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="26fc6-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="26fc6-115">Para establecer - out en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="26fc6-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="26fc6-116">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="26fc6-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="26fc6-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="26fc6-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="26fc6-118">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="26fc6-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="26fc6-119">3.  Modifique el valor en el **nombre de ensamblado** cuadro.</span><span class="sxs-lookup"><span data-stu-id="26fc6-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26fc6-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26fc6-120">Example</span></span>  
 <span data-ttu-id="26fc6-121">El siguiente código compila `T2.vb` y crea el archivo de salida `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="26fc6-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="26fc6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="26fc6-122">See Also</span></span>  
 [<span data-ttu-id="26fc6-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26fc6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="26fc6-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26fc6-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="26fc6-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="26fc6-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
