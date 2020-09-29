---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: cb56e727479fd249cb0d7e5e7c3c50d5b68b3a72
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072020"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="aabf7-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aabf7-102">-define (Visual Basic)</span></span>

<span data-ttu-id="aabf7-103">Permite definir constantes condicionales para el compilador.</span><span class="sxs-lookup"><span data-stu-id="aabf7-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabf7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aabf7-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="aabf7-105">o</span><span class="sxs-lookup"><span data-stu-id="aabf7-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aabf7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aabf7-106">Arguments</span></span>  
  
|<span data-ttu-id="aabf7-107">Término</span><span class="sxs-lookup"><span data-stu-id="aabf7-107">Term</span></span>|<span data-ttu-id="aabf7-108">Definición</span><span class="sxs-lookup"><span data-stu-id="aabf7-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="aabf7-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="aabf7-109">Required.</span></span> <span data-ttu-id="aabf7-110">Símbolo que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="aabf7-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="aabf7-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="aabf7-111">Optional.</span></span> <span data-ttu-id="aabf7-112">Valor que se va a asignar a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="aabf7-112">The value to assign `symbol`.</span></span> <span data-ttu-id="aabf7-113">Si `value` es una cadena, se debe incluir entre secuencias de barra diagonal inversa/ y comillas (\\") en lugar de entre comillas.</span><span class="sxs-lookup"><span data-stu-id="aabf7-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="aabf7-114">Si no se especifica ningún valor, se considera como verdadero.</span><span class="sxs-lookup"><span data-stu-id="aabf7-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aabf7-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aabf7-115">Remarks</span></span>  

 <span data-ttu-id="aabf7-116">La opción `-define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes definidas con `-define` son públicas y se aplican a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="aabf7-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="aabf7-117">Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="aabf7-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="aabf7-118">`-d` es la forma abreviada de `-define`.</span><span class="sxs-lookup"><span data-stu-id="aabf7-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="aabf7-119">Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.</span><span class="sxs-lookup"><span data-stu-id="aabf7-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="aabf7-120">Para establecer -define en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aabf7-120">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="aabf7-121">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="aabf7-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="aabf7-122">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aabf7-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="aabf7-123">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="aabf7-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="aabf7-124">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="aabf7-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="aabf7-125">4.  Cambie el valor del cuadro **Constantes personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="aabf7-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aabf7-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aabf7-126">Example</span></span>  

 <span data-ttu-id="aabf7-127">En el siguiente código se definen y usan dos constantes de compilador condicionales.</span><span class="sxs-lookup"><span data-stu-id="aabf7-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="aabf7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="aabf7-128">See also</span></span>

- [<span data-ttu-id="aabf7-129">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aabf7-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="aabf7-130">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="aabf7-130">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="aabf7-131">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="aabf7-131">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)
- [<span data-ttu-id="aabf7-132">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aabf7-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
