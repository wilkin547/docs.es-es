---
title: Características obsoletas en .NET 5+
description: Obtenga información sobre las API marcadas como obsoletas en .NET 5.0 y versiones posteriores que generan advertencias del compilador SYSLIB.
ms.date: 10/20/2020
ms.openlocfilehash: 336958c93e3db8f66cfbec89476a666e5e103b70
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593310"
---
# <a name="obsolete-features-in-net-5"></a><span data-ttu-id="fb42a-103">Características obsoletas en .NET 5</span><span class="sxs-lookup"><span data-stu-id="fb42a-103">Obsolete features in .NET 5</span></span>

<span data-ttu-id="fb42a-104">A partir de .NET 5.0, algunas API recién marcadas como obsoletas usan dos nuevas propiedades en <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fb42a-104">Starting in .NET 5.0, some APIs that are newly marked as obsolete make use of two new properties on <xref:System.ObsoleteAttribute>.</span></span>

- <span data-ttu-id="fb42a-105">La propiedad <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> indica al compilador que genere advertencias de compilación mediante un identificador de diagnóstico personalizado.</span><span class="sxs-lookup"><span data-stu-id="fb42a-105">The <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> property tells the compiler to generate build warnings using a custom diagnostic ID.</span></span> <span data-ttu-id="fb42a-106">El identificador personalizado permite que las advertencias de obsolescencia se supriman específicamente y de forma independiente entre sí.</span><span class="sxs-lookup"><span data-stu-id="fb42a-106">The custom ID allows for obsoletion warning to be suppressed specifically and separately from one another.</span></span> <span data-ttu-id="fb42a-107">En el caso de las obsolescencias de .NET 5+, el formato del identificador de diagnóstico personalizado es `SYSLIBxxxx`.</span><span class="sxs-lookup"><span data-stu-id="fb42a-107">In the case of the .NET 5+ obsoletions, the format for the custom diagnostic ID is `SYSLIBxxxx`.</span></span>

- <span data-ttu-id="fb42a-108">La propiedad <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> indica al compilador que incluya un vínculo de dirección URL para obtener más información sobre la obsolescencia.</span><span class="sxs-lookup"><span data-stu-id="fb42a-108">The <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> property tells the compiler to include a URL link to learn more about the obsoletion.</span></span>

<span data-ttu-id="fb42a-109">Si se producen advertencias o errores de compilación debido al uso de una API obsoleta, siga las instrucciones específicas proporcionadas para el identificador de diagnóstico en la sección [Referencia](#reference).</span><span class="sxs-lookup"><span data-stu-id="fb42a-109">If you encounter build warnings or errors due to usage of an obsolete API, follow the specific guidance provided for the diagnostic ID listed in the [Reference](#reference) section.</span></span> <span data-ttu-id="fb42a-110">Las advertencias o los errores de estas obsolescencias *no* pueden suprimirse mediante el [identificador de diagnóstico estándar (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) para tipos o miembros obsoletos; use los valores del identificador de diagnóstico `SYSLIBxxxx` personalizado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fb42a-110">Warnings or errors for these obsoletions *can't* be suppressed using the [standard diagnostic ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) for obsolete types or members; use the custom `SYSLIBxxxx` diagnostic ID values instead.</span></span> <span data-ttu-id="fb42a-111">Para obtener más información, vea [Suprimir advertencias](#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="fb42a-111">For more information, see [Suppress warnings](#suppress-warnings).</span></span>

## <a name="reference"></a><span data-ttu-id="fb42a-112">Referencia</span><span class="sxs-lookup"><span data-stu-id="fb42a-112">Reference</span></span>

<span data-ttu-id="fb42a-113">En la tabla siguiente se proporciona un índice de las obsolescencias `SYSLIBxxxx` en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="fb42a-113">The following table provides an index to the `SYSLIBxxxx` obsoletions in .NET 5+.</span></span>

| <span data-ttu-id="fb42a-114">Id. de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="fb42a-114">Diagnostic ID</span></span> | <span data-ttu-id="fb42a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb42a-115">Description</span></span> |
| - | - |
| [<span data-ttu-id="fb42a-116">SYSLIB0001</span><span class="sxs-lookup"><span data-stu-id="fb42a-116">SYSLIB0001</span></span>](syslib-warnings/syslib0001.md) | <span data-ttu-id="fb42a-117">La codificación UTF-7 no es segura y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="fb42a-117">The UTF-7 encoding is insecure and should not be used.</span></span> <span data-ttu-id="fb42a-118">Considere la posibilidad de usar UTF-8 en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fb42a-118">Consider using UTF-8 instead.</span></span> |
| [<span data-ttu-id="fb42a-119">SYSLIB0002</span><span class="sxs-lookup"><span data-stu-id="fb42a-119">SYSLIB0002</span></span>](syslib-warnings/syslib0002.md) | <span data-ttu-id="fb42a-120">El entorno de ejecución no respeta <xref:System.Security.Permissions.PrincipalPermissionAttribute> y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="fb42a-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> is not honored by the runtime and must not be used.</span></span> |
| [<span data-ttu-id="fb42a-121">SYSLIB0003</span><span class="sxs-lookup"><span data-stu-id="fb42a-121">SYSLIB0003</span></span>](syslib-warnings/syslib0003.md) | <span data-ttu-id="fb42a-122">La seguridad de acceso del código (CAS) no es compatible o el entorno de ejecución no la respeta.</span><span class="sxs-lookup"><span data-stu-id="fb42a-122">Code access security (CAS) is not supported or honored by the runtime.</span></span> |
| [<span data-ttu-id="fb42a-123">SYSLIB0004</span><span class="sxs-lookup"><span data-stu-id="fb42a-123">SYSLIB0004</span></span>](syslib-warnings/syslib0004.md) | <span data-ttu-id="fb42a-124">No se admite la característica de regiones de ejecución restringidas (CER).</span><span class="sxs-lookup"><span data-stu-id="fb42a-124">The constrained execution region (CER) feature is not supported.</span></span> |
| [<span data-ttu-id="fb42a-125">SYSLIB0005</span><span class="sxs-lookup"><span data-stu-id="fb42a-125">SYSLIB0005</span></span>](syslib-warnings/syslib0005.md) | <span data-ttu-id="fb42a-126">No se admite la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="fb42a-126">The global assembly cache (GAC) is not supported.</span></span> |
| [<span data-ttu-id="fb42a-127">SYSLIB0006</span><span class="sxs-lookup"><span data-stu-id="fb42a-127">SYSLIB0006</span></span>](syslib-warnings/syslib0006.md) | <span data-ttu-id="fb42a-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> no se admite y produce una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="fb42a-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fb42a-129">SYSLIB0007</span><span class="sxs-lookup"><span data-stu-id="fb42a-129">SYSLIB0007</span></span>](syslib-warnings/syslib0007.md) | <span data-ttu-id="fb42a-130">La implementación predeterminada de este algoritmo de criptografía no es compatible.</span><span class="sxs-lookup"><span data-stu-id="fb42a-130">The default implementation of this cryptography algorithm is not supported.</span></span> |
| [<span data-ttu-id="fb42a-131">SYSLIB0008</span><span class="sxs-lookup"><span data-stu-id="fb42a-131">SYSLIB0008</span></span>](syslib-warnings/syslib0008.md) | <span data-ttu-id="fb42a-132">La API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> no se admite y produce una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="fb42a-132">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fb42a-133">SYSLIB0009</span><span class="sxs-lookup"><span data-stu-id="fb42a-133">SYSLIB0009</span></span>](syslib-warnings/syslib0009.md) | <span data-ttu-id="fb42a-134">Los métodos <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> y <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> no se admiten y producen una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="fb42a-134">The <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> and <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> methods are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fb42a-135">SYSLIB0010</span><span class="sxs-lookup"><span data-stu-id="fb42a-135">SYSLIB0010</span></span>](syslib-warnings/syslib0010.md) | <span data-ttu-id="fb42a-136">No se admiten algunas API de comunicación remota y producen una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="fb42a-136">Some remoting APIs are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fb42a-137">SYSLIB0011</span><span class="sxs-lookup"><span data-stu-id="fb42a-137">SYSLIB0011</span></span>](syslib-warnings/syslib0011.md) | <span data-ttu-id="fb42a-138">La serialización <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> está obsoleta y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="fb42a-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is obsolete and should not be used.</span></span> |
| [<span data-ttu-id="fb42a-139">SYSLIB0012</span><span class="sxs-lookup"><span data-stu-id="fb42a-139">SYSLIB0012</span></span>](syslib-warnings/syslib0012.md) | <span data-ttu-id="fb42a-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> y <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> solo se incluyen para la compatibilidad con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb42a-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> and <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> are only included for .NET Framework compatibility.</span></span> <span data-ttu-id="fb42a-141">Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fb42a-141">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span> |

## <a name="suppress-warnings"></a><span data-ttu-id="fb42a-142">Suprimir advertencias</span><span class="sxs-lookup"><span data-stu-id="fb42a-142">Suppress warnings</span></span>

<span data-ttu-id="fb42a-143">Si debe usar las API obsoletas y el diagnóstico `SYSLIBxxxx` no se ve como un error, puede suprimir la advertencia en el código o en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb42a-143">If you must use the obsolete APIs and the `SYSLIBxxxx` diagnostic does not surface as an error, you can suppress the warning in code or in your project file.</span></span>

<span data-ttu-id="fb42a-144">Mediante código:</span><span class="sxs-lookup"><span data-stu-id="fb42a-144">In code:</span></span>

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

<span data-ttu-id="fb42a-145">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="fb42a-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="fb42a-146">La supresión de advertencias de esta manera solo deshabilita las advertencias de obsolescencia que especifique.</span><span class="sxs-lookup"><span data-stu-id="fb42a-146">Suppressing warnings in this way only disables the obsoletion warnings you specify.</span></span> <span data-ttu-id="fb42a-147">No deshabilita ninguna otra advertencia, incluidas las de obsolescencia con otros identificadores de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fb42a-147">It doesn't disable any other warnings, including obsoletion warnings with different diagnostic IDs.</span></span>
