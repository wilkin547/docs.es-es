---
title: -delaysign
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d659e97f3b3a360456a1fcdaa9756934bb096334
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-delaysign"></a><span data-ttu-id="211a1-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="211a1-102">-delaysign</span></span>
<span data-ttu-id="211a1-103">Especifica si el ensamblado estará firmado total o parcialmente.</span><span class="sxs-lookup"><span data-stu-id="211a1-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="211a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="211a1-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="211a1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="211a1-105">Arguments</span></span>  
 <span data-ttu-id="211a1-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="211a1-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="211a1-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="211a1-107">Optional.</span></span> <span data-ttu-id="211a1-108">Use `-delaysign-` para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="211a1-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="211a1-109">Use `-delaysign+` si desea colocar la clave pública en el ensamblado y reservar espacio para el hash firmado.</span><span class="sxs-lookup"><span data-stu-id="211a1-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="211a1-110">De manera predeterminada, es `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="211a1-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="211a1-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="211a1-111">Remarks</span></span>  
 <span data-ttu-id="211a1-112">El `-delaysign` opción no tiene ningún efecto a menos que use con [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="211a1-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="211a1-113">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="211a1-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="211a1-114">La firma digital resultante se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="211a1-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="211a1-115">Una vez un ensamblado con firma retrasada, el compilador no de proceso y se almacena la firma, pero reserva espacio en el archivo para que la firma se pueda agregar más tarde.</span><span class="sxs-lookup"><span data-stu-id="211a1-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="211a1-116">Por ejemplo, al usar `-delaysign+`, un desarrollador de una organización distribuye versiones de prueba sin firma de un ensamblado que los evaluadores pueden utilizar y registrar con la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="211a1-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="211a1-117">Cuando se completa el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="211a1-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="211a1-118">Esta división de funciones protege la clave privada de la organización contra la divulgación, permitiendo a los desarrolladores trabajar en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="211a1-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="211a1-119">Vea [crear y utilizar ensamblados](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre cómo firmar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="211a1-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="211a1-120">Para establecer - delaysign en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="211a1-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="211a1-121">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="211a1-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="211a1-122">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="211a1-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="211a1-123">Haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="211a1-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="211a1-124">Establezca el valor el **Retrasar firma sólo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="211a1-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211a1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="211a1-125">See Also</span></span>  
 [<span data-ttu-id="211a1-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="211a1-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="211a1-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="211a1-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="211a1-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="211a1-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="211a1-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="211a1-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
