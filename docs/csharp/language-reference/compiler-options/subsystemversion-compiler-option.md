---
description: -subsystemversion (Opciones del compilador de C#)
title: -subsystemversion (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: e8001d8db214123e75fec4e1d1117ef90a9df606
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128600"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="dce1f-103">-subsystemversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="dce1f-103">-subsystemversion (C# Compiler Options)</span></span>

<span data-ttu-id="dce1f-104">Especifica la versión mínima del subsistema en la que se puede ejecutar el archivo ejecutable generado, lo que determina las versiones de Windows en las que se puede ejecutar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="dce1f-104">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="dce1f-105">Normalmente, esta opción garantiza que el archivo ejecutable pueda aprovechar las características de seguridad concretas que no están disponibles en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="dce1f-105">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="dce1f-106">Para especificar el subsistema en sí mismo, use la opción del compilador [-target](./target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dce1f-106">To specify the subsystem itself, use the [-target](./target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="dce1f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dce1f-107">Syntax</span></span>

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="dce1f-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dce1f-108">Parameters</span></span>

`major.minor`

<span data-ttu-id="dce1f-109">La versión mínima requerida del subsistema, expresada en una notación de puntos para las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="dce1f-109">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="dce1f-110">Por ejemplo, puede especificar que una aplicación no se puede ejecutar en un sistema operativo que sea anterior a Windows 7 si establece el valor de esta opción en 6.01, como se describe en la tabla que aparece más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="dce1f-110">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="dce1f-111">Debe especificar los valores de `major` y `minor` como números enteros.</span><span class="sxs-lookup"><span data-stu-id="dce1f-111">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="dce1f-112">Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí.</span><span class="sxs-lookup"><span data-stu-id="dce1f-112">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="dce1f-113">Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente.</span><span class="sxs-lookup"><span data-stu-id="dce1f-113">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="dce1f-114">Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.</span><span class="sxs-lookup"><span data-stu-id="dce1f-114">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="dce1f-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dce1f-115">Remarks</span></span>

<span data-ttu-id="dce1f-116">En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.</span><span class="sxs-lookup"><span data-stu-id="dce1f-116">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="dce1f-117">Versión de Windows</span><span class="sxs-lookup"><span data-stu-id="dce1f-117">Windows version</span></span>|<span data-ttu-id="dce1f-118">Versión de subsistema</span><span class="sxs-lookup"><span data-stu-id="dce1f-118">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="dce1f-119">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="dce1f-119">Windows 2000</span></span>|<span data-ttu-id="dce1f-120">5.00</span><span class="sxs-lookup"><span data-stu-id="dce1f-120">5.00</span></span>|
|<span data-ttu-id="dce1f-121">Windows XP</span><span class="sxs-lookup"><span data-stu-id="dce1f-121">Windows XP</span></span>|<span data-ttu-id="dce1f-122">5.01</span><span class="sxs-lookup"><span data-stu-id="dce1f-122">5.01</span></span>|
|<span data-ttu-id="dce1f-123">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="dce1f-123">Windows Server 2003</span></span>|<span data-ttu-id="dce1f-124">5.02</span><span class="sxs-lookup"><span data-stu-id="dce1f-124">5.02</span></span>|
|<span data-ttu-id="dce1f-125">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="dce1f-125">Windows Vista</span></span>|<span data-ttu-id="dce1f-126">6.00</span><span class="sxs-lookup"><span data-stu-id="dce1f-126">6.00</span></span>|
|<span data-ttu-id="dce1f-127">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dce1f-127">Windows 7</span></span>|<span data-ttu-id="dce1f-128">6.01</span><span class="sxs-lookup"><span data-stu-id="dce1f-128">6.01</span></span>|
|<span data-ttu-id="dce1f-129">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="dce1f-129">Windows Server 2008</span></span>|<span data-ttu-id="dce1f-130">6.01</span><span class="sxs-lookup"><span data-stu-id="dce1f-130">6.01</span></span>|
|<span data-ttu-id="dce1f-131">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dce1f-131">Windows 8</span></span>|<span data-ttu-id="dce1f-132">6.02</span><span class="sxs-lookup"><span data-stu-id="dce1f-132">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="dce1f-133">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="dce1f-133">Default values</span></span>

<span data-ttu-id="dce1f-134">El valor predeterminado de la opción del compilador **-subsystemversion** depende de las condiciones de esta lista:</span><span class="sxs-lookup"><span data-stu-id="dce1f-134">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="dce1f-135">El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="dce1f-135">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="dce1f-136">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="dce1f-136">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)

  - [<span data-ttu-id="dce1f-137">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="dce1f-137">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)

  - [<span data-ttu-id="dce1f-138">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="dce1f-138">-platform:arm</span></span>](./platform-compiler-option.md)

- <span data-ttu-id="dce1f-139">El valor predeterminado es 6,00 si usa MSBuild, tiene como destino .NET Framework 4.5 y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.</span><span class="sxs-lookup"><span data-stu-id="dce1f-139">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="dce1f-140">El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="dce1f-140">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="dce1f-141">Establecer esta opción</span><span class="sxs-lookup"><span data-stu-id="dce1f-141">Setting this option</span></span>

<span data-ttu-id="dce1f-142">Para establecer la opción del compilador **-subsystemversion** en Visual Studio, debe abrir el archivo .csproj y especificar un valor para la propiedad `SubsystemVersion` en el XML de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="dce1f-142">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="dce1f-143">No se puede establecer esta opción en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dce1f-143">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="dce1f-144">Para obtener más información, consulte la sección "Valores predeterminados" que aparece más arriba en este tema o [Propiedades comunes de proyectos de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="dce1f-144">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="dce1f-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="dce1f-145">See also</span></span>

- [<span data-ttu-id="dce1f-146">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="dce1f-146">C# Compiler Options</span></span>](./index.md)
