---
title: -delaysign (Opciones del compilador de C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970441"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="62ad4-102">-delaysign (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="62ad4-102">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="62ad4-103">Esta opción hace que el compilador reserve espacio en el archivo de salida de manera que se pueda agregar una firma digital más adelante.</span><span class="sxs-lookup"><span data-stu-id="62ad4-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="62ad4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62ad4-104">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="62ad4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="62ad4-105">Arguments</span></span>

<span data-ttu-id="62ad4-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="62ad4-106">`+` &#124; `-`</span></span>

<span data-ttu-id="62ad4-107">Use **-delaysign-** para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="62ad4-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="62ad4-108">Use **-delaysign+** si quiere incluir solo la clave pública en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="62ad4-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="62ad4-109">El valor predeterminado es **-delaysign-** .</span><span class="sxs-lookup"><span data-stu-id="62ad4-109">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="62ad4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62ad4-110">Remarks</span></span>

<span data-ttu-id="62ad4-111">La opción **-delaysign** no tiene ningún efecto a menos que se use con [-keyfile](./keyfile-compiler-option.md) o [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="62ad4-111">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="62ad4-112">Las opciones **-delaysign** y **-publicsign** son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="62ad4-112">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="62ad4-113">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="62ad4-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="62ad4-114">Esta operación crea una firma digital que se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="62ad4-114">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="62ad4-115">Cuando se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.</span><span class="sxs-lookup"><span data-stu-id="62ad4-115">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="62ad4-116">Por ejemplo, si se usa **-delaysign+** , los evaluadores podrán colocar el ensamblado en la memoria caché global.</span><span class="sxs-lookup"><span data-stu-id="62ad4-116">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="62ad4-117">Después de realizar las pruebas, coloque la clave privada en el ensamblado mediante la utilidad [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) para firmar el ensamblado por completo.</span><span class="sxs-lookup"><span data-stu-id="62ad4-117">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="62ad4-118">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) y [Retraso de la firma de un ensamblado](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="62ad4-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="62ad4-119">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="62ad4-119">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="62ad4-120">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="62ad4-120">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="62ad4-121">Modifique la propiedad **Solo retrasar firma**.</span><span class="sxs-lookup"><span data-stu-id="62ad4-121">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="62ad4-122">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="62ad4-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="62ad4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="62ad4-123">See also</span></span>

- [<span data-ttu-id="62ad4-124">Opción C# -publicsign</span><span class="sxs-lookup"><span data-stu-id="62ad4-124">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="62ad4-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="62ad4-125">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="62ad4-126">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="62ad4-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
