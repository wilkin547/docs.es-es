---
title: -nostdlib (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 70007c74efe9a41bdfc15e8fa7daf3c8fc0221ed
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935529"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="755e2-102">-nostdlib (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="755e2-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="755e2-103">**-nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.</span><span class="sxs-lookup"><span data-stu-id="755e2-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="755e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="755e2-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="755e2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="755e2-105">Remarks</span></span>

<span data-ttu-id="755e2-106">Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.</span><span class="sxs-lookup"><span data-stu-id="755e2-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="755e2-107">Si no se especifica **-nostdlib**, el archivo mscorlib.dll se importa en el programa (equivale a especificar **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="755e2-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="755e2-108">Especificar **-nostdlib** es lo mismo que especificar **-nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="755e2-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="755e2-109">Para establecer esta opción del compilador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="755e2-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="755e2-110">Las instrucciones siguientes solo se aplican a Visual Studio 2015 (y versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="755e2-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="755e2-111">La propiedad de compilación **No hacer referencia a mscorlib.dll** no existe en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="755e2-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="755e2-112">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="755e2-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="755e2-113">Haga clic en la página de propiedades de **Compilar** .</span><span class="sxs-lookup"><span data-stu-id="755e2-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="755e2-114">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="755e2-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="755e2-115">Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="755e2-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="755e2-116">Para establecer esta opción del compilador mediante programación</span><span class="sxs-lookup"><span data-stu-id="755e2-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="755e2-117">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="755e2-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="755e2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="755e2-118">See Also</span></span>

- [<span data-ttu-id="755e2-119">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="755e2-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
