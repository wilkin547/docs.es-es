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
ms.openlocfilehash: c5bb11bc62e951339113f4b48e98e05362490ca1
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="main"></a><span data-ttu-id="0950d-102">/main</span><span class="sxs-lookup"><span data-stu-id="0950d-102">/main</span></span>
<span data-ttu-id="0950d-103">Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="0950d-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0950d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0950d-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="0950d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0950d-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="0950d-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="0950d-106">Required.</span></span> <span data-ttu-id="0950d-107">Una calificación completa a la clase o módulo que contiene el `Sub Main` procedimiento al que llamar cuando se inicia el programa.</span><span class="sxs-lookup"><span data-stu-id="0950d-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="0950d-108">Esto puede tener el formato **/main:module** o **Module**.</span><span class="sxs-lookup"><span data-stu-id="0950d-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0950d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0950d-109">Remarks</span></span>  
 <span data-ttu-id="0950d-110">Utilice esta opción cuando se crea un archivo ejecutable o un programa ejecutable de Windows.</span><span class="sxs-lookup"><span data-stu-id="0950d-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="0950d-111">Si el **/main** opción se omite, el compilador busca válido compartido `Sub Main` en todos los módulos y las clases públicas.</span><span class="sxs-lookup"><span data-stu-id="0950d-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="0950d-112">Vea [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para obtener una explicación de las distintas formas de la `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0950d-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="0950d-113">Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un valor predeterminado `Main` procedimiento que inicia la aplicación si la clase no tiene ningún `Main` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0950d-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="0950d-114">Esto le permite compilar el código en la línea de comandos que se creó en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="0950d-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="0950d-115">Para establecer /main en Visual Studio integra el entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="0950d-115">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="0950d-116">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="0950d-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0950d-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0950d-117">On the **Project** menu, click **Properties**.</span></span>  
  
       
  
2.  <span data-ttu-id="0950d-118">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="0950d-118">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="0950d-119">Asegúrese de que el **marco de aplicación de habilitar** no está activada la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="0950d-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="0950d-120">Modifique el valor en el **objeto de inicio** cuadro.</span><span class="sxs-lookup"><span data-stu-id="0950d-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0950d-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0950d-121">Example</span></span>  
 <span data-ttu-id="0950d-122">El siguiente código compila `T2.vb` y `T3.vb`, especificando que la `Sub Main` procedimiento se encuentra en la `Test2` clase.</span><span class="sxs-lookup"><span data-stu-id="0950d-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="0950d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0950d-123">See Also</span></span>  
 [<span data-ttu-id="0950d-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0950d-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0950d-125">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0950d-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="0950d-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0950d-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="0950d-127">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0950d-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
