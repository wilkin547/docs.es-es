---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2697b837a536b1b879196bd10843a2b76314747a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="main"></a><span data-ttu-id="c8d06-102">/main</span><span class="sxs-lookup"><span data-stu-id="c8d06-102">/main</span></span>
<span data-ttu-id="c8d06-103">Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="c8d06-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8d06-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8d06-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c8d06-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="c8d06-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c8d06-106">Required.</span></span> <span data-ttu-id="c8d06-107">Una calificación completa a la clase o módulo que contiene el `Sub Main` procedimiento al que llamar cuando se inicia el programa.</span><span class="sxs-lookup"><span data-stu-id="c8d06-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="c8d06-108">Esto puede tener el formato **/main:module** o **Module**.</span><span class="sxs-lookup"><span data-stu-id="c8d06-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8d06-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8d06-109">Remarks</span></span>  
 <span data-ttu-id="c8d06-110">Utilice esta opción cuando se crea un archivo ejecutable o un programa ejecutable de Windows.</span><span class="sxs-lookup"><span data-stu-id="c8d06-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="c8d06-111">Si el **/main** opción se omite, el compilador busca válido compartido `Sub Main` en todos los módulos y las clases públicas.</span><span class="sxs-lookup"><span data-stu-id="c8d06-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="c8d06-112">Vea [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para obtener una explicación de las distintas formas de la `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c8d06-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="c8d06-113">Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un valor predeterminado `Main` procedimiento que inicia la aplicación si la clase no tiene ningún `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c8d06-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="c8d06-114">Esto le permite compilar el código en la línea de comandos que se creó en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="c8d06-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="c8d06-115">Para establecer /main en Visual Studio integra el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="c8d06-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="c8d06-116">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="c8d06-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c8d06-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c8d06-117">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="c8d06-118">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="c8d06-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="c8d06-119">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="c8d06-119">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="c8d06-120">Asegúrese de que el **marco de aplicación de habilitar** no está activada la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="c8d06-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="c8d06-121">Modifique el valor en el **objeto de inicio** cuadro.</span><span class="sxs-lookup"><span data-stu-id="c8d06-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8d06-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8d06-122">Example</span></span>  
 <span data-ttu-id="c8d06-123">El siguiente código compila `T2.vb` y `T3.vb`, especificando que la `Sub Main` procedimiento se encuentra en la `Test2` clase.</span><span class="sxs-lookup"><span data-stu-id="c8d06-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8d06-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8d06-124">See Also</span></span>  
 [<span data-ttu-id="c8d06-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d06-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c8d06-126">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8d06-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="c8d06-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8d06-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c8d06-128">NIB: versión de Visual Basic de Hola a todos</span><span class="sxs-lookup"><span data-stu-id="c8d06-128">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="c8d06-129">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8d06-129">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
