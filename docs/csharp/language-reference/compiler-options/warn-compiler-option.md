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
ms.openlocfilehash: 5b05e944a37e16fc1fcc422271be00c09a271a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602408"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="b2768-102">-warn (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b2768-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="b2768-103">La opción **-warn** especifica el nivel de advertencia que debe mostrar el compilador.</span><span class="sxs-lookup"><span data-stu-id="b2768-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2768-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2768-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2768-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b2768-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="b2768-106">El nivel de advertencia que quiere que se muestre para la compilación: los números más bajos muestran solo advertencias de gravedad alta; los números más altos muestran más advertencias.</span><span class="sxs-lookup"><span data-stu-id="b2768-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="b2768-107">Los valores válidos son 0 a 4:</span><span class="sxs-lookup"><span data-stu-id="b2768-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="b2768-108">Nivel de advertencia</span><span class="sxs-lookup"><span data-stu-id="b2768-108">Warning level</span></span>|<span data-ttu-id="b2768-109">Significado</span><span class="sxs-lookup"><span data-stu-id="b2768-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="b2768-110">0</span><span class="sxs-lookup"><span data-stu-id="b2768-110">0</span></span>|<span data-ttu-id="b2768-111">Desactiva la emisión de todos los mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="b2768-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="b2768-112">1</span><span class="sxs-lookup"><span data-stu-id="b2768-112">1</span></span>|<span data-ttu-id="b2768-113">Muestra mensajes de advertencia graves.</span><span class="sxs-lookup"><span data-stu-id="b2768-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="b2768-114">2</span><span class="sxs-lookup"><span data-stu-id="b2768-114">2</span></span>|<span data-ttu-id="b2768-115">Muestra advertencias de nivel 1 además de determinadas advertencias menos graves, como advertencias sobre ocultar miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="b2768-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="b2768-116">3</span><span class="sxs-lookup"><span data-stu-id="b2768-116">3</span></span>|<span data-ttu-id="b2768-117">Muestra advertencias de nivel 2 además de determinadas advertencias menos graves, como advertencias sobre expresiones que siempre se evalúan como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="b2768-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="b2768-118">4 (el valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b2768-118">4 (the default)</span></span>|<span data-ttu-id="b2768-119">Muestra todas las advertencias de nivel 3 además de advertencias informativas.</span><span class="sxs-lookup"><span data-stu-id="b2768-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2768-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2768-120">Remarks</span></span>  
 <span data-ttu-id="b2768-121">Para obtener información sobre un error o advertencia, puede buscar el código de error en el Índice de la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="b2768-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="b2768-122">Para conocer otras maneras de obtener información sobre un error o advertencia, vea [Errores del compilador de C#](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2768-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="b2768-123">Use [-warnaserror](./warnaserror-compiler-option.md) para tratar todas las advertencias como errores.</span><span class="sxs-lookup"><span data-stu-id="b2768-123">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="b2768-124">Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.</span><span class="sxs-lookup"><span data-stu-id="b2768-124">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="b2768-125">**-w** es la forma abreviada de **-warn**.</span><span class="sxs-lookup"><span data-stu-id="b2768-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b2768-126">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2768-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="b2768-127">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2768-127">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="b2768-128">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="b2768-128">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="b2768-129">Modifique la propiedad de **Nivel de advertencia**.</span><span class="sxs-lookup"><span data-stu-id="b2768-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="b2768-130">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2768-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2768-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2768-131">Example</span></span>  
 <span data-ttu-id="b2768-132">Compile `in.cs` y haga que el compilador solo muestre advertencias de nivel 1:</span><span class="sxs-lookup"><span data-stu-id="b2768-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2768-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2768-133">See also</span></span>

- [<span data-ttu-id="b2768-134">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="b2768-134">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="b2768-135">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="b2768-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
