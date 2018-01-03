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
ms.openlocfilehash: 62669ec40803170cb623382b09472b82121d26bb
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="define-visual-basic"></a><span data-ttu-id="52ed0-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ed0-102">/define (Visual Basic)</span></span>
<span data-ttu-id="52ed0-103">Permite definir constantes condicionales para el compilador.</span><span class="sxs-lookup"><span data-stu-id="52ed0-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ed0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52ed0-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="52ed0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="52ed0-105">Arguments</span></span>  
  
|<span data-ttu-id="52ed0-106">Término</span><span class="sxs-lookup"><span data-stu-id="52ed0-106">Term</span></span>|<span data-ttu-id="52ed0-107">Definición</span><span class="sxs-lookup"><span data-stu-id="52ed0-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="52ed0-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="52ed0-108">Required.</span></span> <span data-ttu-id="52ed0-109">Símbolo que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="52ed0-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="52ed0-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="52ed0-110">Optional.</span></span> <span data-ttu-id="52ed0-111">Valor que se va a asignar a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="52ed0-111">The value to assign `symbol`.</span></span> <span data-ttu-id="52ed0-112">Si `value` es una cadena, debe incluirse entre secuencias de barra diagonal inversa/comillas (\\") en lugar de comillas.</span><span class="sxs-lookup"><span data-stu-id="52ed0-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="52ed0-113">Si no se especifica ningún valor, se considera como verdadero.</span><span class="sxs-lookup"><span data-stu-id="52ed0-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52ed0-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52ed0-114">Remarks</span></span>  
 <span data-ttu-id="52ed0-115">La opción `/define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes con `/define` son públicas y se aplican a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="52ed0-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="52ed0-116">Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="52ed0-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="52ed0-117">`/d` es la forma abreviada de `/define`.</span><span class="sxs-lookup"><span data-stu-id="52ed0-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="52ed0-118">Se pueden definir varios símbolos con `/define`; use una coma para separar las definiciones de símbolos.</span><span class="sxs-lookup"><span data-stu-id="52ed0-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="52ed0-119">Para definir/establecer en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52ed0-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="52ed0-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="52ed0-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="52ed0-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="52ed0-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="52ed0-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="52ed0-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="52ed0-123">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="52ed0-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="52ed0-124">4.  Modifique el valor en el **constantes personalizadas** cuadro.</span><span class="sxs-lookup"><span data-stu-id="52ed0-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="52ed0-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52ed0-125">Example</span></span>  
 <span data-ttu-id="52ed0-126">En el siguiente código se definen y usan dos constantes de compilador condicionales.</span><span class="sxs-lookup"><span data-stu-id="52ed0-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="52ed0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ed0-127">See Also</span></span>  
 [<span data-ttu-id="52ed0-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52ed0-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="52ed0-129">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="52ed0-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="52ed0-130">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="52ed0-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="52ed0-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="52ed0-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
