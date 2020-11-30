---
description: -warn (Opciones del compilador de C#)
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
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: d59274423e6f9844d3ab22f3ac513ba1a05d7f07
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91171356"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="b2789-103">-warn (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b2789-103">-warn (C# Compiler Options)</span></span>

<span data-ttu-id="b2789-104">La opción **-warn** especifica el nivel de advertencia que debe mostrar el compilador.</span><span class="sxs-lookup"><span data-stu-id="b2789-104">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2789-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2789-105">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2789-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b2789-106">Arguments</span></span>  

 `option`  
 <span data-ttu-id="b2789-107">El nivel de advertencia que quiere que se muestre para la compilación: los números más bajos muestran solo advertencias de gravedad alta; los números más altos muestran más advertencias.</span><span class="sxs-lookup"><span data-stu-id="b2789-107">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="b2789-108">El valor debe ser cero o un entero positivo:</span><span class="sxs-lookup"><span data-stu-id="b2789-108">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="b2789-109">Nivel de advertencia</span><span class="sxs-lookup"><span data-stu-id="b2789-109">Warning level</span></span>|<span data-ttu-id="b2789-110">Significado</span><span class="sxs-lookup"><span data-stu-id="b2789-110">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="b2789-111">0</span><span class="sxs-lookup"><span data-stu-id="b2789-111">0</span></span>|<span data-ttu-id="b2789-112">Desactiva la emisión de todos los mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="b2789-112">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="b2789-113">1</span><span class="sxs-lookup"><span data-stu-id="b2789-113">1</span></span>|<span data-ttu-id="b2789-114">Muestra mensajes de advertencia graves.</span><span class="sxs-lookup"><span data-stu-id="b2789-114">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="b2789-115">2</span><span class="sxs-lookup"><span data-stu-id="b2789-115">2</span></span>|<span data-ttu-id="b2789-116">Muestra advertencias de nivel 1 además de determinadas advertencias menos graves, como advertencias sobre ocultar miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="b2789-116">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="b2789-117">3</span><span class="sxs-lookup"><span data-stu-id="b2789-117">3</span></span>|<span data-ttu-id="b2789-118">Muestra advertencias de nivel 2 además de determinadas advertencias menos graves, como advertencias sobre expresiones que siempre se evalúan como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="b2789-118">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="b2789-119">4 (el valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b2789-119">4 (the default)</span></span>|<span data-ttu-id="b2789-120">Muestra todas las advertencias de nivel 3 además de advertencias informativas.</span><span class="sxs-lookup"><span data-stu-id="b2789-120">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="b2789-121">5</span><span class="sxs-lookup"><span data-stu-id="b2789-121">5</span></span>|<span data-ttu-id="b2789-122">Muestra las advertencias de nivel 4, además de [advertencias adicionales](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) del compilador incluido con C# 9.0.</span><span class="sxs-lookup"><span data-stu-id="b2789-122">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="b2789-123">Mayor que 5</span><span class="sxs-lookup"><span data-stu-id="b2789-123">Greater than 5</span></span>|<span data-ttu-id="b2789-124">Cualquier valor mayor que 5 se tratará como 5.</span><span class="sxs-lookup"><span data-stu-id="b2789-124">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="b2789-125">Normalmente, se proporciona un valor grande arbitrario (por ejemplo, `9999`) para asegurarse de que siempre reciba todas las advertencias si el compilador se actualiza con nuevos niveles de advertencia.</span><span class="sxs-lookup"><span data-stu-id="b2789-125">You generally put arbitrary large value (for example, `9999`) to make sure you always have all warnings if the compiler is updated with new warning levels.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="b2789-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b2789-126">Remarks</span></span>  

 <span data-ttu-id="b2789-127">Para obtener información sobre un error o advertencia, puede buscar el código de error en el Índice de la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="b2789-127">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="b2789-128">Para conocer otras maneras de obtener información sobre un error o advertencia, vea [Errores del compilador de C#](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2789-128">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="b2789-129">Use [-warnaserror](./warnaserror-compiler-option.md) para tratar todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="b2789-129">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="b2789-130">Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="b2789-130">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="b2789-131">**-w** es la forma abreviada de **-warn**.</span><span class="sxs-lookup"><span data-stu-id="b2789-131">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b2789-132">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2789-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="b2789-133">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2789-133">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="b2789-134">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="b2789-134">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="b2789-135">Modifique la propiedad de **Nivel de advertencia**.</span><span class="sxs-lookup"><span data-stu-id="b2789-135">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="b2789-136">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2789-136">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2789-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2789-137">Example</span></span>  

 <span data-ttu-id="b2789-138">Compile `in.cs` y haga que el compilador solo muestre advertencias de nivel 1:</span><span class="sxs-lookup"><span data-stu-id="b2789-138">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2789-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2789-139">See also</span></span>

- [<span data-ttu-id="b2789-140">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="b2789-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="b2789-141">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="b2789-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
