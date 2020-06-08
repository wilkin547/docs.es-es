---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408704"
---
# <a name="-delaysign"></a><span data-ttu-id="bf3ff-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="bf3ff-102">-delaysign</span></span>

<span data-ttu-id="bf3ff-103">Especifica si el ensamblado estará firmado total o parcialmente.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf3ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf3ff-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="bf3ff-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bf3ff-105">Arguments</span></span>

<span data-ttu-id="bf3ff-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bf3ff-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="bf3ff-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-107">Optional.</span></span> <span data-ttu-id="bf3ff-108">Use `-delaysign-` para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="bf3ff-109">Use `-delaysign+` si quiere colocar la clave pública en el ensamblado y reservar espacio para el hash firmado.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="bf3ff-110">De manera predeterminada, es `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf3ff-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf3ff-111">Remarks</span></span>

<span data-ttu-id="bf3ff-112">La opción `-delaysign` no tiene ningún efecto a menos que se use con [-keyfile](keyfile.md) o [-keycontainer](keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="bf3ff-112">The `-delaysign` option has no effect unless used with [-keyfile](keyfile.md) or [-keycontainer](keycontainer.md).</span></span>

<span data-ttu-id="bf3ff-113">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="bf3ff-114">La firma digital resultante se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="bf3ff-115">Si se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="bf3ff-116">Por ejemplo, mediante el uso de `-delaysign+`, un desarrollador de una organización puede distribuir versiones de prueba sin firmar de un ensamblado que los evaluadores pueden registrar con la caché global de ensamblados y usar.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="bf3ff-117">Cuando se completa el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="bf3ff-118">Esta compartimentación protege la clave privada de la organización contra la divulgación, a la vez que permite que todos los desarrolladores trabajen en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="bf3ff-119">Para obtener más información sobre cómo firmar un ensamblado, vea [Crear y utilizar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="bf3ff-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="bf3ff-120">Para establecer -delaysign en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf3ff-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="bf3ff-121">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bf3ff-122">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="bf3ff-123">Haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="bf3ff-124">Establezca el valor en el cuadro **Solo retrasar firma**.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf3ff-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf3ff-125">See also</span></span>

- [<span data-ttu-id="bf3ff-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf3ff-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="bf3ff-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="bf3ff-127">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="bf3ff-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="bf3ff-128">-keycontainer</span></span>](keycontainer.md)
- [<span data-ttu-id="bf3ff-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf3ff-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
