---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 5dcf9dc5cc0987e965aba7fd2b8821252e19a655
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788900"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="fc0cc-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc0cc-102">-out (Visual Basic)</span></span>
<span data-ttu-id="fc0cc-103">Especifica el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc0cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc0cc-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc0cc-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fc0cc-105">Arguments</span></span>  
  
|<span data-ttu-id="fc0cc-106">Término</span><span class="sxs-lookup"><span data-stu-id="fc0cc-106">Term</span></span>|<span data-ttu-id="fc0cc-107">Definición</span><span class="sxs-lookup"><span data-stu-id="fc0cc-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="fc0cc-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-108">Required.</span></span> <span data-ttu-id="fc0cc-109">El nombre del archivo de salida que crea el compilador.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="fc0cc-110">Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="fc0cc-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc0cc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc0cc-111">Remarks</span></span>  
 <span data-ttu-id="fc0cc-112">Especifique el nombre completo y la extensión de archivo que se creará.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="fc0cc-113">Si no lo hace, el archivo .exe toma su nombre de archivo de código fuente que contiene el `Sub Main` procedimiento y el archivo .dll adopta el nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="fc0cc-114">Si especifica un nombre de archivo sin extensión .exe o .dll, el compilador agrega automáticamente la extensión para usted, dependiendo del valor especificado para el `-target` opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="fc0cc-115">Para establecer - out en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc0cc-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="fc0cc-116">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fc0cc-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="fc0cc-118">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="fc0cc-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="fc0cc-119">3.  Modifique el valor en el **nombre del ensamblado** cuadro.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc0cc-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc0cc-120">Example</span></span>  
 <span data-ttu-id="fc0cc-121">El siguiente código compila `T2.vb` y crea el archivo de salida `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="fc0cc-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc0cc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc0cc-122">See also</span></span>

- [<span data-ttu-id="fc0cc-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc0cc-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fc0cc-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc0cc-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="fc0cc-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc0cc-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
