---
description: Más información sobre -out (Visual Basic)
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 82fb43ecf2239c38245f3afe7cacef8bad573175
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475895"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="ea657-103">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea657-103">-out (Visual Basic)</span></span>

<span data-ttu-id="ea657-104">Especifica el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="ea657-104">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea657-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea657-105">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea657-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ea657-106">Arguments</span></span>  
  
|<span data-ttu-id="ea657-107">Término</span><span class="sxs-lookup"><span data-stu-id="ea657-107">Term</span></span>|<span data-ttu-id="ea657-108">Definición</span><span class="sxs-lookup"><span data-stu-id="ea657-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="ea657-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea657-109">Required.</span></span> <span data-ttu-id="ea657-110">El nombre del archivo de salida creado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="ea657-110">The name of the output file the compiler creates.</span></span> <span data-ttu-id="ea657-111">Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").</span><span class="sxs-lookup"><span data-stu-id="ea657-111">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea657-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea657-112">Remarks</span></span>  

 <span data-ttu-id="ea657-113">Especifique el nombre completo y la extensión del archivo que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ea657-113">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="ea657-114">Si no lo hace, el archivo .exe toma su nombre del archivo de código fuente que contiene el procedimiento `Sub Main` y el archivo .dll toma el suyo del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="ea657-114">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="ea657-115">Si especifica un nombre de archivo sin la extensión .exe o .dll, el compilador agrega automáticamente la extensión, en función del valor especificado para la opción del compilador `-target`.</span><span class="sxs-lookup"><span data-stu-id="ea657-115">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="ea657-116">Para establecer -out en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ea657-116">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ea657-117">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ea657-117">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ea657-118">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ea657-118">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ea657-119">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="ea657-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="ea657-120">3.  Modifique el valor del cuadro **Nombre del ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="ea657-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ea657-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea657-121">Example</span></span>  

 <span data-ttu-id="ea657-122">El código siguiente compila `T2.vb` y crea el archivo de salida `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="ea657-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea657-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea657-123">See also</span></span>

- [<span data-ttu-id="ea657-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea657-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ea657-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea657-125">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ea657-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea657-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
