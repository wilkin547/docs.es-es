---
description: -delaysign (Opciones del compilador de C#)
title: -delaysign (Opciones del compilador de C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 5512ebeca4672f5d69852ab07c3f3fa40c305327
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125844"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="2be13-103">-delaysign (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="2be13-103">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="2be13-104">Esta opción hace que el compilador reserve espacio en el archivo de salida de manera que se pueda agregar una firma digital más adelante.</span><span class="sxs-lookup"><span data-stu-id="2be13-104">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="2be13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2be13-105">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="2be13-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2be13-106">Arguments</span></span>

<span data-ttu-id="2be13-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2be13-107">`+` &#124; `-`</span></span>

<span data-ttu-id="2be13-108">Use **-delaysign-** para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2be13-108">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="2be13-109">Use **-delaysign+** si quiere incluir solo la clave pública en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2be13-109">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="2be13-110">El valor predeterminado es **-delaysign-** .</span><span class="sxs-lookup"><span data-stu-id="2be13-110">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="2be13-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2be13-111">Remarks</span></span>

<span data-ttu-id="2be13-112">La opción **-delaysign** no tiene ningún efecto a menos que se use con [-keyfile](./keyfile-compiler-option.md) o [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="2be13-112">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="2be13-113">Las opciones **-delaysign** y **-publicsign** son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="2be13-113">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="2be13-114">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="2be13-114">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="2be13-115">Esta operación crea una firma digital que se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="2be13-115">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="2be13-116">Cuando se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.</span><span class="sxs-lookup"><span data-stu-id="2be13-116">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="2be13-117">Por ejemplo, si se usa **-delaysign+**, los evaluadores podrán colocar el ensamblado en la memoria caché global.</span><span class="sxs-lookup"><span data-stu-id="2be13-117">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="2be13-118">Después de realizar las pruebas, coloque la clave privada en el ensamblado mediante la utilidad [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) para firmar el ensamblado por completo.</span><span class="sxs-lookup"><span data-stu-id="2be13-118">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="2be13-119">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Retraso de la firma de un ensamblado](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="2be13-119">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2be13-120">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2be13-120">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="2be13-121">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2be13-121">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="2be13-122">Modifique la propiedad **Solo retrasar firma**.</span><span class="sxs-lookup"><span data-stu-id="2be13-122">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="2be13-123">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="2be13-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="2be13-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2be13-124">See also</span></span>

- [<span data-ttu-id="2be13-125">Opción C# -publicsign</span><span class="sxs-lookup"><span data-stu-id="2be13-125">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="2be13-126">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="2be13-126">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="2be13-127">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="2be13-127">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
