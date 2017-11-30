---
title: /define (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bc3056c3e2d7a4aad469d3bf2c404f5f5248384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="define-visual-basic"></a><span data-ttu-id="bc0cf-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc0cf-102">/define (Visual Basic)</span></span>
<span data-ttu-id="bc0cf-103">Permite definir constantes condicionales para el compilador.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc0cf-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc0cf-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bc0cf-105">Arguments</span></span>  
  
|<span data-ttu-id="bc0cf-106">Término</span><span class="sxs-lookup"><span data-stu-id="bc0cf-106">Term</span></span>|<span data-ttu-id="bc0cf-107">Definición</span><span class="sxs-lookup"><span data-stu-id="bc0cf-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="bc0cf-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-108">Required.</span></span> <span data-ttu-id="bc0cf-109">Símbolo que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="bc0cf-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-110">Optional.</span></span> <span data-ttu-id="bc0cf-111">Valor que se va a asignar a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-111">The value to assign `symbol`.</span></span> <span data-ttu-id="bc0cf-112">Si `value` es una cadena, debe incluirse entre secuencias de barra diagonal inversa/comillas (\\") en lugar de comillas.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="bc0cf-113">Si no se especifica ningún valor, se considera como verdadero.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc0cf-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc0cf-114">Remarks</span></span>  
 <span data-ttu-id="bc0cf-115">La opción `/define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes con `/define` son públicas y se aplican a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="bc0cf-116">Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="bc0cf-117">`/d` es la forma abreviada de `/define`.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="bc0cf-118">Se pueden definir varios símbolos con `/define`; use una coma para separar las definiciones de símbolos.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="bc0cf-119">Para definir/establecer en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bc0cf-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="bc0cf-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bc0cf-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-121">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="bc0cf-122">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="bc0cf-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="bc0cf-123">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="bc0cf-124">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="bc0cf-125">4.  Modifique el valor en el **constantes personalizadas** cuadro.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bc0cf-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc0cf-126">Example</span></span>  
 <span data-ttu-id="bc0cf-127">En el siguiente código se definen y usan dos constantes de compilador condicionales.</span><span class="sxs-lookup"><span data-stu-id="bc0cf-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bc0cf-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc0cf-128">See Also</span></span>  
 [<span data-ttu-id="bc0cf-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc0cf-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bc0cf-130">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="bc0cf-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="bc0cf-131">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="bc0cf-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="bc0cf-132">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc0cf-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
