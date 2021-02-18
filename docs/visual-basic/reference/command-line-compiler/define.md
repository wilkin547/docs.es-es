---
description: Más información sobre -define (Visual Basic)
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
ms.openlocfilehash: 9d6394ecad8e59d64ef3c51312ac85562ba3ec2c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466983"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="9599b-103">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9599b-103">-define (Visual Basic)</span></span>

<span data-ttu-id="9599b-104">Permite definir constantes condicionales para el compilador.</span><span class="sxs-lookup"><span data-stu-id="9599b-104">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9599b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9599b-105">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="9599b-106">o</span><span class="sxs-lookup"><span data-stu-id="9599b-106">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9599b-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9599b-107">Arguments</span></span>  
  
|<span data-ttu-id="9599b-108">Término</span><span class="sxs-lookup"><span data-stu-id="9599b-108">Term</span></span>|<span data-ttu-id="9599b-109">Definición</span><span class="sxs-lookup"><span data-stu-id="9599b-109">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="9599b-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9599b-110">Required.</span></span> <span data-ttu-id="9599b-111">Símbolo que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="9599b-111">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="9599b-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9599b-112">Optional.</span></span> <span data-ttu-id="9599b-113">Valor que se va a asignar a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="9599b-113">The value to assign `symbol`.</span></span> <span data-ttu-id="9599b-114">Si `value` es una cadena, se debe incluir entre secuencias de barra diagonal inversa/ y comillas (\\") en lugar de entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9599b-114">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="9599b-115">Si no se especifica ningún valor, se considera como verdadero.</span><span class="sxs-lookup"><span data-stu-id="9599b-115">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9599b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9599b-116">Remarks</span></span>  

 <span data-ttu-id="9599b-117">La opción `-define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes definidas con `-define` son públicas y se aplican a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9599b-117">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="9599b-118">Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="9599b-118">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="9599b-119">`-d` es la forma abreviada de `-define`.</span><span class="sxs-lookup"><span data-stu-id="9599b-119">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="9599b-120">Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9599b-120">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="9599b-121">Para establecer -define en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9599b-121">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9599b-122">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="9599b-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9599b-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9599b-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="9599b-124">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="9599b-124">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="9599b-125">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="9599b-125">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="9599b-126">4.  Cambie el valor del cuadro **Constantes personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="9599b-126">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9599b-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9599b-127">Example</span></span>  

 <span data-ttu-id="9599b-128">En el siguiente código se definen y usan dos constantes de compilador condicionales.</span><span class="sxs-lookup"><span data-stu-id="9599b-128">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="9599b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9599b-129">See also</span></span>

- [<span data-ttu-id="9599b-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9599b-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9599b-131">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="9599b-131">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="9599b-132">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="9599b-132">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)
- [<span data-ttu-id="9599b-133">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9599b-133">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
