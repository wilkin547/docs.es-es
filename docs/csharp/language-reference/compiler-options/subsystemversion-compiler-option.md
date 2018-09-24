---
title: -subsystemversion (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: ff4cd196edc1ec04f8abcecfa1a7a4e99e32dd56
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46508869"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="573dd-102">-subsystemversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="573dd-102">-subsystemversion (C# Compiler Options)</span></span>
<span data-ttu-id="573dd-103">Especifica la versión mínima del subsistema en la que se puede ejecutar el archivo ejecutable generado, lo que determina las versiones de Windows en las que se puede ejecutar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="573dd-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="573dd-104">Normalmente, esta opción garantiza que el archivo ejecutable pueda aprovechar las características de seguridad concretas que no están disponibles en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="573dd-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="573dd-105">Para especificar el subsistema en sí mismo, use la opción del compilador [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="573dd-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573dd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="573dd-106">Syntax</span></span>  
  
```console  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="573dd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="573dd-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="573dd-108">La versión mínima requerida del subsistema, expresada en una notación de puntos para las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="573dd-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="573dd-109">Por ejemplo, puede especificar que una aplicación no se puede ejecutar en un sistema operativo que sea anterior a Windows 7 si establece el valor de esta opción en 6.01, como se describe en la tabla que aparece más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="573dd-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="573dd-110">Debe especificar los valores de `major` y `minor` como números enteros.</span><span class="sxs-lookup"><span data-stu-id="573dd-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="573dd-111">Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí.</span><span class="sxs-lookup"><span data-stu-id="573dd-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="573dd-112">Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente.</span><span class="sxs-lookup"><span data-stu-id="573dd-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="573dd-113">Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.</span><span class="sxs-lookup"><span data-stu-id="573dd-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="573dd-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="573dd-114">Remarks</span></span>  
 <span data-ttu-id="573dd-115">En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.</span><span class="sxs-lookup"><span data-stu-id="573dd-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="573dd-116">Versión de Windows</span><span class="sxs-lookup"><span data-stu-id="573dd-116">Windows version</span></span>|<span data-ttu-id="573dd-117">Versión de subsistema</span><span class="sxs-lookup"><span data-stu-id="573dd-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="573dd-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="573dd-118">Windows 2000</span></span>|<span data-ttu-id="573dd-119">5.00</span><span class="sxs-lookup"><span data-stu-id="573dd-119">5.00</span></span>|  
|<span data-ttu-id="573dd-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="573dd-120">Windows XP</span></span>|<span data-ttu-id="573dd-121">5.01</span><span class="sxs-lookup"><span data-stu-id="573dd-121">5.01</span></span>|  
|<span data-ttu-id="573dd-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="573dd-122">Windows Server 2003</span></span>|<span data-ttu-id="573dd-123">5.02</span><span class="sxs-lookup"><span data-stu-id="573dd-123">5.02</span></span>|  
|<span data-ttu-id="573dd-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="573dd-124">Windows Vista</span></span>|<span data-ttu-id="573dd-125">6.00</span><span class="sxs-lookup"><span data-stu-id="573dd-125">6.00</span></span>|  
|<span data-ttu-id="573dd-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="573dd-126">Windows 7</span></span>|<span data-ttu-id="573dd-127">6.01</span><span class="sxs-lookup"><span data-stu-id="573dd-127">6.01</span></span>|  
|<span data-ttu-id="573dd-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="573dd-128">Windows Server 2008</span></span>|<span data-ttu-id="573dd-129">6.01</span><span class="sxs-lookup"><span data-stu-id="573dd-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="573dd-130">6.02</span><span class="sxs-lookup"><span data-stu-id="573dd-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="573dd-131">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="573dd-131">Default values</span></span>  
 <span data-ttu-id="573dd-132">El valor predeterminado de la opción del compilador **-subsystemversion** depende de las condiciones de esta lista:</span><span class="sxs-lookup"><span data-stu-id="573dd-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="573dd-133">El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="573dd-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="573dd-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="573dd-134">-target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [<span data-ttu-id="573dd-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="573dd-135">-target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [<span data-ttu-id="573dd-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="573dd-136">-platform:arm</span></span>](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   <span data-ttu-id="573dd-137">El valor predeterminado es 6.00 si usa MSBuild, tiene como destino [!INCLUDE[net_v45](~/includes/net-v45-md.md)] y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.</span><span class="sxs-lookup"><span data-stu-id="573dd-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="573dd-138">El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="573dd-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="573dd-139">Establecer esta opción</span><span class="sxs-lookup"><span data-stu-id="573dd-139">Setting this option</span></span>  
 <span data-ttu-id="573dd-140">Para establecer la opción del compilador **-subsystemversion** en Visual Studio, debe abrir el archivo .csproj y especificar un valor para la propiedad `SubsystemVersion` en el XML de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="573dd-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="573dd-141">No se puede establecer esta opción en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="573dd-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="573dd-142">Para obtener más información, consulte la sección "Valores predeterminados" que aparece más arriba en este tema o [Propiedades comunes de proyectos de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="573dd-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573dd-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="573dd-143">See Also</span></span>  

- [<span data-ttu-id="573dd-144">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="573dd-144">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
