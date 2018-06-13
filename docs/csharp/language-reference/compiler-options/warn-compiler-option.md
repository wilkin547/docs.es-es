---
title: -warn (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 65a6348bb0364d79ed0e69daf3a31ea7aa1bf8ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218876"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="67cdf-102">-warn (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="67cdf-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="67cdf-103">La opción **-warn** especifica el nivel de advertencia que debe mostrar el compilador.</span><span class="sxs-lookup"><span data-stu-id="67cdf-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67cdf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67cdf-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="67cdf-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="67cdf-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="67cdf-106">El nivel de advertencia que quiere que se muestre para la compilación: los números más bajos muestran solo advertencias de gravedad alta; los números más altos muestran más advertencias.</span><span class="sxs-lookup"><span data-stu-id="67cdf-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="67cdf-107">Los valores válidos son 0 a 4:</span><span class="sxs-lookup"><span data-stu-id="67cdf-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="67cdf-108">Nivel de advertencia</span><span class="sxs-lookup"><span data-stu-id="67cdf-108">Warning level</span></span>|<span data-ttu-id="67cdf-109">Significado</span><span class="sxs-lookup"><span data-stu-id="67cdf-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="67cdf-110">0</span><span class="sxs-lookup"><span data-stu-id="67cdf-110">0</span></span>|<span data-ttu-id="67cdf-111">Desactiva la emisión de todos los mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="67cdf-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="67cdf-112">1</span><span class="sxs-lookup"><span data-stu-id="67cdf-112">1</span></span>|<span data-ttu-id="67cdf-113">Muestra mensajes de advertencia graves.</span><span class="sxs-lookup"><span data-stu-id="67cdf-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="67cdf-114">2</span><span class="sxs-lookup"><span data-stu-id="67cdf-114">2</span></span>|<span data-ttu-id="67cdf-115">Muestra advertencias de nivel 1 además de determinadas advertencias menos graves, como advertencias sobre ocultar miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="67cdf-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="67cdf-116">3</span><span class="sxs-lookup"><span data-stu-id="67cdf-116">3</span></span>|<span data-ttu-id="67cdf-117">Muestra advertencias de nivel 2 además de determinadas advertencias menos graves, como advertencias sobre expresiones que siempre se evalúan como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="67cdf-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="67cdf-118">4 (el valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="67cdf-118">4 (the default)</span></span>|<span data-ttu-id="67cdf-119">Muestra todas las advertencias de nivel 3 además de advertencias informativas.</span><span class="sxs-lookup"><span data-stu-id="67cdf-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67cdf-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67cdf-120">Remarks</span></span>  
 <span data-ttu-id="67cdf-121">Para obtener información sobre un error o advertencia, puede buscar el código de error en el Índice de la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="67cdf-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="67cdf-122">Para conocer otras maneras de obtener información sobre un error o advertencia, vea [Errores del compilador de C#](../../../csharp/language-reference/compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="67cdf-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="67cdf-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) para tratar todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="67cdf-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="67cdf-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) para deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="67cdf-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="67cdf-125">**-w** es la forma abreviada de **-warn**.</span><span class="sxs-lookup"><span data-stu-id="67cdf-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="67cdf-126">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="67cdf-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="67cdf-127">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="67cdf-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="67cdf-128">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="67cdf-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="67cdf-129">Modifique la propiedad de **Nivel de advertencia**.</span><span class="sxs-lookup"><span data-stu-id="67cdf-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="67cdf-130">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="67cdf-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67cdf-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67cdf-131">Example</span></span>  
 <span data-ttu-id="67cdf-132">Compile `in.cs` y haga que el compilador solo muestre advertencias de nivel 1:</span><span class="sxs-lookup"><span data-stu-id="67cdf-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="67cdf-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="67cdf-133">See Also</span></span>  
 [<span data-ttu-id="67cdf-134">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="67cdf-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="67cdf-135">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="67cdf-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
