---
title: -subsystemversion (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9369f87f62bd2f481c543f6cdbb3344ac841193e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="82b09-102">-subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82b09-102">-subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="82b09-103">Especifica la versión mínima del subsistema en la que se puede ejecutar el archivo ejecutable generado, lo que determina las versiones de Windows en las que se puede ejecutar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="82b09-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="82b09-104">Normalmente, esta opción garantiza que el archivo ejecutable pueda aprovechar las características de seguridad concretas que no están disponibles en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="82b09-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82b09-105">Para especificar el subsistema en sí mismo, use la opción del compilador [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="82b09-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b09-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82b09-106">Syntax</span></span>  
  
```vb  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82b09-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82b09-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="82b09-108">La versión mínima requerida del subsistema, expresada en una notación de puntos para las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="82b09-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="82b09-109">Por ejemplo, puede especificar que una aplicación no se puede ejecutar en un sistema operativo que sea anterior a Windows 7 si establece el valor de esta opción en 6.01, como se describe en la tabla que aparece más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="82b09-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="82b09-110">Debe especificar los valores de `major` y `minor` como números enteros.</span><span class="sxs-lookup"><span data-stu-id="82b09-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="82b09-111">Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí.</span><span class="sxs-lookup"><span data-stu-id="82b09-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="82b09-112">Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente.</span><span class="sxs-lookup"><span data-stu-id="82b09-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="82b09-113">Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.</span><span class="sxs-lookup"><span data-stu-id="82b09-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82b09-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82b09-114">Remarks</span></span>  
 <span data-ttu-id="82b09-115">En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.</span><span class="sxs-lookup"><span data-stu-id="82b09-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="82b09-116">Versión de Windows</span><span class="sxs-lookup"><span data-stu-id="82b09-116">Windows version</span></span>|<span data-ttu-id="82b09-117">Versión de subsistema</span><span class="sxs-lookup"><span data-stu-id="82b09-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="82b09-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="82b09-118">Windows 2000</span></span>|<span data-ttu-id="82b09-119">5.00</span><span class="sxs-lookup"><span data-stu-id="82b09-119">5.00</span></span>|  
|<span data-ttu-id="82b09-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="82b09-120">Windows XP</span></span>|<span data-ttu-id="82b09-121">5.01</span><span class="sxs-lookup"><span data-stu-id="82b09-121">5.01</span></span>|  
|<span data-ttu-id="82b09-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="82b09-122">Windows Server 2003</span></span>|<span data-ttu-id="82b09-123">5.02</span><span class="sxs-lookup"><span data-stu-id="82b09-123">5.02</span></span>|  
|<span data-ttu-id="82b09-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="82b09-124">Windows Vista</span></span>|<span data-ttu-id="82b09-125">6.00</span><span class="sxs-lookup"><span data-stu-id="82b09-125">6.00</span></span>|  
|<span data-ttu-id="82b09-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="82b09-126">Windows 7</span></span>|<span data-ttu-id="82b09-127">6.01</span><span class="sxs-lookup"><span data-stu-id="82b09-127">6.01</span></span>|  
|<span data-ttu-id="82b09-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="82b09-128">Windows Server 2008</span></span>|<span data-ttu-id="82b09-129">6.01</span><span class="sxs-lookup"><span data-stu-id="82b09-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="82b09-130">6.02</span><span class="sxs-lookup"><span data-stu-id="82b09-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="82b09-131">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="82b09-131">Default values</span></span>  
 <span data-ttu-id="82b09-132">El valor predeterminado de la opción del compilador **-subsystemversion** depende de las condiciones de esta lista:</span><span class="sxs-lookup"><span data-stu-id="82b09-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="82b09-133">El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="82b09-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="82b09-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="82b09-134">-target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="82b09-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="82b09-135">-target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="82b09-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="82b09-136">-platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="82b09-137">El valor predeterminado es 6.00 si usa MSBuild, tiene como destino [!INCLUDE[net_v45](~/includes/net-v45-md.md)] y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.</span><span class="sxs-lookup"><span data-stu-id="82b09-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="82b09-138">El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="82b09-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="82b09-139">Establecer esta opción</span><span class="sxs-lookup"><span data-stu-id="82b09-139">Setting this option</span></span>  
 <span data-ttu-id="82b09-140">Para establecer el **- subsystemversion** opción del compilador en Visual Studio, debe abrir el archivo .vbproj y especifique un valor para el `SubsystemVersion` propiedad en el XML de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="82b09-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="82b09-141">No se puede establecer esta opción en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="82b09-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="82b09-142">Para obtener más información, consulte la sección "Valores predeterminados" que aparece más arriba en este tema o [Propiedades comunes de proyectos de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="82b09-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="82b09-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="82b09-143">See Also</span></span>  
[<span data-ttu-id="82b09-144">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82b09-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="82b09-145">Propiedades de MSBuild</span><span class="sxs-lookup"><span data-stu-id="82b09-145">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
