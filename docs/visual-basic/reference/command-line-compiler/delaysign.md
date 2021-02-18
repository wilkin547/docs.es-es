---
description: Más información sobre -delaysign
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: fc3e52f63431da870355e369e6ffeb8b7b14c5ab
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461507"
---
# <a name="-delaysign"></a><span data-ttu-id="b10a3-103">-delaysign</span><span class="sxs-lookup"><span data-stu-id="b10a3-103">-delaysign</span></span>

<span data-ttu-id="b10a3-104">Especifica si el ensamblado estará firmado total o parcialmente.</span><span class="sxs-lookup"><span data-stu-id="b10a3-104">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b10a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b10a3-105">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="b10a3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b10a3-106">Arguments</span></span>

<span data-ttu-id="b10a3-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b10a3-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="b10a3-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b10a3-108">Optional.</span></span> <span data-ttu-id="b10a3-109">Use `-delaysign-` para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b10a3-109">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="b10a3-110">Use `-delaysign+` si quiere colocar la clave pública en el ensamblado y reservar espacio para el hash firmado.</span><span class="sxs-lookup"><span data-stu-id="b10a3-110">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="b10a3-111">De manera predeterminada, es `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="b10a3-111">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b10a3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b10a3-112">Remarks</span></span>

<span data-ttu-id="b10a3-113">La opción `-delaysign` no tiene ningún efecto a menos que se use con [-keyfile](keyfile.md) o [-keycontainer](keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="b10a3-113">The `-delaysign` option has no effect unless used with [-keyfile](keyfile.md) or [-keycontainer](keycontainer.md).</span></span>

<span data-ttu-id="b10a3-114">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="b10a3-114">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="b10a3-115">La firma digital resultante se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="b10a3-115">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="b10a3-116">Si se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.</span><span class="sxs-lookup"><span data-stu-id="b10a3-116">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="b10a3-117">Por ejemplo, mediante el uso de `-delaysign+`, un desarrollador de una organización puede distribuir versiones de prueba sin firmar de un ensamblado que los evaluadores pueden registrar con la caché global de ensamblados y usar.</span><span class="sxs-lookup"><span data-stu-id="b10a3-117">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="b10a3-118">Cuando se completa el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b10a3-118">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="b10a3-119">Esta compartimentación protege la clave privada de la organización contra la divulgación, a la vez que permite que todos los desarrolladores trabajen en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b10a3-119">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="b10a3-120">Para obtener más información sobre cómo firmar un ensamblado, vea [Crear y utilizar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="b10a3-120">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="b10a3-121">Para establecer -delaysign en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b10a3-121">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="b10a3-122">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="b10a3-122">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b10a3-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b10a3-123">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="b10a3-124">Haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="b10a3-124">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="b10a3-125">Establezca el valor en el cuadro **Solo retrasar firma**.</span><span class="sxs-lookup"><span data-stu-id="b10a3-125">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="b10a3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b10a3-126">See also</span></span>

- [<span data-ttu-id="b10a3-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b10a3-127">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b10a3-128">-keyfile</span><span class="sxs-lookup"><span data-stu-id="b10a3-128">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="b10a3-129">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="b10a3-129">-keycontainer</span></span>](keycontainer.md)
- [<span data-ttu-id="b10a3-130">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b10a3-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
