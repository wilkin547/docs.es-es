---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005509"
---
# <a name="-main"></a><span data-ttu-id="b04f1-102">-main</span><span class="sxs-lookup"><span data-stu-id="b04f1-102">-main</span></span>
<span data-ttu-id="b04f1-103">Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="b04f1-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b04f1-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="b04f1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b04f1-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="b04f1-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b04f1-106">Required.</span></span> <span data-ttu-id="b04f1-107">Nombre de la clase o módulo que contiene el procedimiento `Sub Main` que se va a llamar cuando se inicie el programa.</span><span class="sxs-lookup"><span data-stu-id="b04f1-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="b04f1-108">Puede tener el formato **-Main: module** o **-Main: Namespace. Module**.</span><span class="sxs-lookup"><span data-stu-id="b04f1-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b04f1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b04f1-109">Remarks</span></span>  
 <span data-ttu-id="b04f1-110">Utilice esta opción cuando cree un archivo ejecutable o un programa ejecutable de Windows.</span><span class="sxs-lookup"><span data-stu-id="b04f1-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="b04f1-111">Si se omite la opción **-Main** , el compilador busca un @no__t compartido válido en todas las clases y módulos públicos.</span><span class="sxs-lookup"><span data-stu-id="b04f1-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="b04f1-112">Vea el [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para obtener una explicación de las distintas formas del procedimiento `Main`.</span><span class="sxs-lookup"><span data-stu-id="b04f1-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="b04f1-113">Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un procedimiento predeterminado @no__t 2 que inicia la aplicación si la clase no tiene ningún procedimiento `Main`.</span><span class="sxs-lookup"><span data-stu-id="b04f1-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="b04f1-114">Esto le permite compilar código en la línea de comandos que se creó en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b04f1-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="b04f1-115">Para establecer-Main en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b04f1-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="b04f1-116">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="b04f1-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b04f1-117">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b04f1-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="b04f1-118">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="b04f1-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="b04f1-119">Asegúrese de que la casilla **Habilitar marco de aplicación** no esté activada.</span><span class="sxs-lookup"><span data-stu-id="b04f1-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="b04f1-120">Modifique el valor en el cuadro **objeto de inicio** .</span><span class="sxs-lookup"><span data-stu-id="b04f1-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b04f1-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b04f1-121">Example</span></span>  
 <span data-ttu-id="b04f1-122">El código siguiente compila `T2.vb` y `T3.vb`, especificando que el procedimiento `Sub Main` se encontrará en la clase `Test2`.</span><span class="sxs-lookup"><span data-stu-id="b04f1-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="b04f1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b04f1-123">See also</span></span>

- [<span data-ttu-id="b04f1-124">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b04f1-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b04f1-125">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b04f1-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="b04f1-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b04f1-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b04f1-127">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b04f1-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
