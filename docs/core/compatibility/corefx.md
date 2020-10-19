---
title: Cambios importantes de la biblioteca de clases base
description: Muestra los cambios importantes en las bibliotecas básicas de .NET.
ms.date: 07/27/2020
ms.openlocfilehash: d4deef295479b1f32bd72a69369a11c7375835f4
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955568"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="a1ba8-103">Cambios importantes en las bibliotecas principales de .NET</span><span class="sxs-lookup"><span data-stu-id="a1ba8-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="a1ba8-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a1ba8-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="a1ba8-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="a1ba8-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a1ba8-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="a1ba8-106">Breaking change</span></span> | <span data-ttu-id="a1ba8-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a1ba8-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a1ba8-108">Cambios de comportamiento de API relacionados con ensamblados para el formato de publicación de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="a1ba8-108">Assembly-related API behavior changes for single-file publishing format</span></span>](#assembly-related-api-behavior-changes-for-single-file-publishing-format) | <span data-ttu-id="a1ba8-109">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-109">5.0</span></span> |
| [<span data-ttu-id="a1ba8-110">Se ha invertido el orden de las etiquetas en Activity.Tags</span><span class="sxs-lookup"><span data-stu-id="a1ba8-110">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="a1ba8-111">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-111">5.0</span></span> |
| [<span data-ttu-id="a1ba8-112">Nombres de parámetros modificados en RC1</span><span class="sxs-lookup"><span data-stu-id="a1ba8-112">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="a1ba8-113">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-113">5.0</span></span> |
| [<span data-ttu-id="a1ba8-114">Atributos de OSPlatform que se han cambiado de nombre o se han quitado</span><span class="sxs-lookup"><span data-stu-id="a1ba8-114">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="a1ba8-115">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-115">5.0</span></span> |
| [<span data-ttu-id="a1ba8-116">Thread.Abort obsoleto</span><span class="sxs-lookup"><span data-stu-id="a1ba8-116">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="a1ba8-117">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-117">5.0</span></span> |
| [<span data-ttu-id="a1ba8-118">Propiedades obsoletas en ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="a1ba8-118">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="a1ba8-119">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-119">5.0</span></span> |
| [<span data-ttu-id="a1ba8-120">Las comprobaciones intrínsecas de IsSupported de hardware pueden diferir en los tipos anidados</span><span class="sxs-lookup"><span data-stu-id="a1ba8-120">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="a1ba8-121">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-121">5.0</span></span> |
| [<span data-ttu-id="a1ba8-122">Nombres de parámetros modificados en ensamblados de referencia</span><span class="sxs-lookup"><span data-stu-id="a1ba8-122">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="a1ba8-123">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-123">5.0</span></span> |
| [<span data-ttu-id="a1ba8-124">Rutas de acceso de URI con caracteres que no son ASCII se analizan correctamente en UNIX</span><span class="sxs-lookup"><span data-stu-id="a1ba8-124">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="a1ba8-125">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-125">5.0</span></span> |
| [<span data-ttu-id="a1ba8-126">Reconocimiento de URI de rutas UNC en UNIX</span><span class="sxs-lookup"><span data-stu-id="a1ba8-126">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="a1ba8-127">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-127">5.0</span></span> |
| [<span data-ttu-id="a1ba8-128">Environment.OSVersion devuelve la versión correcta del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a1ba8-128">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="a1ba8-129">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-129">5.0</span></span> |
| [<span data-ttu-id="a1ba8-130">Aumento de la complejidad de LINQ OrderBy.First{OrDefault}</span><span class="sxs-lookup"><span data-stu-id="a1ba8-130">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="a1ba8-131">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-131">5.0</span></span> |
| [<span data-ttu-id="a1ba8-132">IntPtr y UIntPtr implementan IFormattable</span><span class="sxs-lookup"><span data-stu-id="a1ba8-132">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="a1ba8-133">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-133">5.0</span></span> |
| [<span data-ttu-id="a1ba8-134">PrincipalPermissionAttribute está obsoleto como error</span><span class="sxs-lookup"><span data-stu-id="a1ba8-134">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="a1ba8-135">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-135">5.0</span></span> |
| [<span data-ttu-id="a1ba8-136">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a1ba8-136">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="a1ba8-137">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-137">5.0</span></span> |
| [<span data-ttu-id="a1ba8-138">Las rutas de acceso al código UTF-7 están obsoletas</span><span class="sxs-lookup"><span data-stu-id="a1ba8-138">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="a1ba8-139">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-139">5.0</span></span> |
| [<span data-ttu-id="a1ba8-140">Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="a1ba8-140">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="a1ba8-141">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-141">5.0</span></span> |
| [<span data-ttu-id="a1ba8-142">El valor predeterminado de ActivityIdFormat es W3C</span><span class="sxs-lookup"><span data-stu-id="a1ba8-142">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="a1ba8-143">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-143">5.0</span></span> |
| [<span data-ttu-id="a1ba8-144">Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="a1ba8-144">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="a1ba8-145">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-145">5.0</span></span> |
| [<span data-ttu-id="a1ba8-146">Los métodos CompareGreaterThan de SSE y SSE2 controlan correctamente las entradas NaN</span><span class="sxs-lookup"><span data-stu-id="a1ba8-146">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="a1ba8-147">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-147">5.0</span></span> |
| [<span data-ttu-id="a1ba8-148">CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia</span><span class="sxs-lookup"><span data-stu-id="a1ba8-148">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="a1ba8-149">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-149">5.0</span></span> |
| [<span data-ttu-id="a1ba8-150">Retirada del paquete Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="a1ba8-150">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="a1ba8-151">5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-151">5.0</span></span> |
| [<span data-ttu-id="a1ba8-152">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="a1ba8-152">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="a1ba8-153">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-153">3.0</span></span> |
| [<span data-ttu-id="a1ba8-154">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="a1ba8-154">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="a1ba8-155">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-155">3.0</span></span> |
| [<span data-ttu-id="a1ba8-156">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="a1ba8-156">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="a1ba8-157">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-157">3.0</span></span> |
| [<span data-ttu-id="a1ba8-158">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="a1ba8-158">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="a1ba8-159">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-159">3.0</span></span> |
| [<span data-ttu-id="a1ba8-160">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="a1ba8-160">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="a1ba8-161">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-161">3.0</span></span> |
| [<span data-ttu-id="a1ba8-162">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="a1ba8-162">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="a1ba8-163">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-163">3.0</span></span> |
| [<span data-ttu-id="a1ba8-164">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="a1ba8-164">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="a1ba8-165">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-165">3.0</span></span> |
| [<span data-ttu-id="a1ba8-166">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="a1ba8-166">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="a1ba8-167">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-167">3.0</span></span> |
| [<span data-ttu-id="a1ba8-168">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="a1ba8-168">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="a1ba8-169">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-169">3.0</span></span> |
| [<span data-ttu-id="a1ba8-170">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="a1ba8-170">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="a1ba8-171">2.1</span><span class="sxs-lookup"><span data-stu-id="a1ba8-171">2.1</span></span> |
| [<span data-ttu-id="a1ba8-172">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="a1ba8-172">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="a1ba8-173">2.1</span><span class="sxs-lookup"><span data-stu-id="a1ba8-173">2.1</span></span> |
| [<span data-ttu-id="a1ba8-174">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="a1ba8-174">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="a1ba8-175">2.1</span><span class="sxs-lookup"><span data-stu-id="a1ba8-175">2.1</span></span> |
| [<span data-ttu-id="a1ba8-176">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="a1ba8-176">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="a1ba8-177">1.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-177">1.0</span></span> |
| [<span data-ttu-id="a1ba8-178">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="a1ba8-178">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="a1ba8-179">1.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-179">1.0</span></span> |
| [<span data-ttu-id="a1ba8-180">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="a1ba8-180">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="a1ba8-181">1.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-181">1.0</span></span> |
| [<span data-ttu-id="a1ba8-182">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="a1ba8-182">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="a1ba8-183">1.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-183">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="a1ba8-184">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-184">.NET 5.0</span></span>

[!INCLUDE [assembly-api-behavior-changes-for-single-file-publish](../../../includes/core-changes/corefx/5.0/assembly-api-behavior-changes-for-single-file-publish.md)]

***

[!INCLUDE [reverse-order-of-tags-in-activity-property](../../../includes/core-changes/corefx/5.0/reverse-order-of-tags-in-activity-property.md)]

***

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

***

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

***

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

***

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

***

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

***

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

***

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

***

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

***

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

***

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

***

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

***

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

***

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

***

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="a1ba8-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-185">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="a1ba8-186">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a1ba8-186">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="a1ba8-187">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="a1ba8-187">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
