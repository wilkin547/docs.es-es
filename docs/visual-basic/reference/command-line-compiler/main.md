---
description: Más información sobre -main
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 4c225c5a0030de6de0aaa510080a586272aa920b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455670"
---
# <a name="-main"></a><span data-ttu-id="0f0bc-103">-main</span><span class="sxs-lookup"><span data-stu-id="0f0bc-103">-main</span></span>

<span data-ttu-id="0f0bc-104">Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-104">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f0bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f0bc-105">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f0bc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0f0bc-106">Arguments</span></span>  

 `location`  
 <span data-ttu-id="0f0bc-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-107">Required.</span></span> <span data-ttu-id="0f0bc-108">Nombre de la clase o módulo que contiene el procedimiento `Sub Main` al que se va a llamar cuando el programa se inicia.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-108">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="0f0bc-109">Puede tener el formato **-main:module** o **-main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-109">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f0bc-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f0bc-110">Remarks</span></span>  

 <span data-ttu-id="0f0bc-111">Use esta opción al crear un archivo ejecutable o un programa ejecutable de Windows.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-111">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="0f0bc-112">Si la opción **-main** se omite, el compilador busca un elemento `Sub Main` compartido válido en todas las clases y módulos públicos.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-112">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="0f0bc-113">Vea [Procedimiento Main en Visual Basic](../../programming-guide/program-structure/main-procedure.md) para obtener una explicación de los distintos formatos del procedimiento `Main`.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-113">See [Main Procedure in Visual Basic](../../programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="0f0bc-114">Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un procedimiento `Main` predeterminado que inicia la aplicación si la clase no tiene un procedimiento `Main`.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-114">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="0f0bc-115">Esto permite compilar código en la línea de comandos que se creó en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-115">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="0f0bc-116">Para definir -main en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0f0bc-116">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="0f0bc-117">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0f0bc-118">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-118">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="0f0bc-119">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="0f0bc-119">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="0f0bc-120">Asegúrese de que la casilla **Habilitar marco de trabajo de la aplicación** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="0f0bc-121">Modifique el valor del cuadro **Objeto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f0bc-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f0bc-122">Example</span></span>  

 <span data-ttu-id="0f0bc-123">En el siguiente código se compilan `T2.vb` y `T3.vb`, especificando que el procedimiento `Sub Main` va a estar en la clase `Test2`.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f0bc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f0bc-124">See also</span></span>

- [<span data-ttu-id="0f0bc-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f0bc-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0f0bc-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f0bc-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="0f0bc-127">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f0bc-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="0f0bc-128">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f0bc-128">Main Procedure in Visual Basic</span></span>](../../programming-guide/program-structure/main-procedure.md)
