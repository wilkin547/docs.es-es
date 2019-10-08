---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005332"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="1491a-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1491a-102">-out (Visual Basic)</span></span>
<span data-ttu-id="1491a-103">Especifica el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="1491a-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1491a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1491a-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="1491a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1491a-105">Arguments</span></span>  
  
|<span data-ttu-id="1491a-106">Término</span><span class="sxs-lookup"><span data-stu-id="1491a-106">Term</span></span>|<span data-ttu-id="1491a-107">Definición</span><span class="sxs-lookup"><span data-stu-id="1491a-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="1491a-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1491a-108">Required.</span></span> <span data-ttu-id="1491a-109">Nombre del archivo de salida que crea el compilador.</span><span class="sxs-lookup"><span data-stu-id="1491a-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="1491a-110">Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="1491a-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1491a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1491a-111">Remarks</span></span>  
 <span data-ttu-id="1491a-112">Especifique el nombre completo y la extensión del archivo que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="1491a-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="1491a-113">Si no lo hace, el archivo. exe toma su nombre del archivo de código fuente que contiene el procedimiento `Sub Main` y el archivo. dll toma su nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1491a-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="1491a-114">Si especifica un nombre de archivo sin la extensión. exe o. dll, el compilador agrega automáticamente la extensión, en función del valor especificado para la opción del compilador `-target`.</span><span class="sxs-lookup"><span data-stu-id="1491a-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="1491a-115">Para establecer en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1491a-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1491a-116">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="1491a-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1491a-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1491a-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1491a-118">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="1491a-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="1491a-119">3.  Modifique el valor en el cuadro **nombre de ensamblado** .</span><span class="sxs-lookup"><span data-stu-id="1491a-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1491a-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1491a-120">Example</span></span>  
 <span data-ttu-id="1491a-121">El siguiente código compila `T2.vb` y crea el archivo de salida `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="1491a-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="1491a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1491a-122">See also</span></span>

- [<span data-ttu-id="1491a-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1491a-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1491a-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1491a-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="1491a-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1491a-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
