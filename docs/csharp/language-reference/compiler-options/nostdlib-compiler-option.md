---
description: -nostdlib (Opciones del compilador de C#)
title: -nostdlib (Opciones del compilador de C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125103"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="afdbc-103">-nostdlib (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="afdbc-103">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="afdbc-104">**-nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.</span><span class="sxs-lookup"><span data-stu-id="afdbc-104">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="afdbc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afdbc-105">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="afdbc-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="afdbc-106">Remarks</span></span>

<span data-ttu-id="afdbc-107">Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.</span><span class="sxs-lookup"><span data-stu-id="afdbc-107">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="afdbc-108">Si no se especifica **-nostdlib**, el archivo mscorlib.dll se importa en el programa (equivale a especificar **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="afdbc-108">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="afdbc-109">Especificar **-nostdlib** es lo mismo que especificar **-nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="afdbc-109">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="afdbc-110">Para establecer esta opción del compilador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="afdbc-110">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="afdbc-111">Las instrucciones siguientes solo se aplican a Visual Studio 2015 (y versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="afdbc-111">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="afdbc-112">La propiedad de compilación **No hacer referencia a mscorlib.dll** no existe en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="afdbc-112">The **Do not reference mscorlib.dll** build property doesn't exist in newer versions of Visual Studio.</span></span>

1. <span data-ttu-id="afdbc-113">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="afdbc-113">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="afdbc-114">Haga clic en la página de propiedades de **Compilar** .</span><span class="sxs-lookup"><span data-stu-id="afdbc-114">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="afdbc-115">Haga clic en el botón **Avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="afdbc-115">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="afdbc-116">Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="afdbc-116">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="afdbc-117">Para establecer esta opción del compilador mediante programación</span><span class="sxs-lookup"><span data-stu-id="afdbc-117">To set this compiler option programmatically</span></span>

<span data-ttu-id="afdbc-118">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="afdbc-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="afdbc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="afdbc-119">See also</span></span>

- [<span data-ttu-id="afdbc-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="afdbc-120">C# Compiler Options</span></span>](./index.md)
