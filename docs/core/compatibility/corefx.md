---
title: Cambios importantes de la biblioteca de clases base
description: Muestra los cambios importantes en las bibliotecas básicas de .NET.
ms.date: 07/27/2020
ms.openlocfilehash: c8eb5ec7d2bb1879a38a18337463230c7b731d29
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137499"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="4e877-103">Cambios importantes en las bibliotecas principales de .NET</span><span class="sxs-lookup"><span data-stu-id="4e877-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="4e877-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e877-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="4e877-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="4e877-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="4e877-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="4e877-106">Breaking change</span></span> | <span data-ttu-id="4e877-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4e877-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="4e877-108">Aumento de la complejidad de LINQ OrderBy.First{OrDefault}</span><span class="sxs-lookup"><span data-stu-id="4e877-108">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="4e877-109">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-109">5.0</span></span> |
| [<span data-ttu-id="4e877-110">IntPtr y UIntPtr implementan IFormattable</span><span class="sxs-lookup"><span data-stu-id="4e877-110">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="4e877-111">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-111">5.0</span></span> |
| [<span data-ttu-id="4e877-112">PrincipalPermissionAttribute está obsoleto como error</span><span class="sxs-lookup"><span data-stu-id="4e877-112">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="4e877-113">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-113">5.0</span></span> |
| [<span data-ttu-id="4e877-114">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4e877-114">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="4e877-115">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-115">5.0</span></span> |
| [<span data-ttu-id="4e877-116">Las rutas de acceso al código UTF-7 están obsoletas</span><span class="sxs-lookup"><span data-stu-id="4e877-116">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="4e877-117">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-117">5.0</span></span> |
| [<span data-ttu-id="4e877-118">Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="4e877-118">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="4e877-119">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-119">5.0</span></span> |
| [<span data-ttu-id="4e877-120">El valor predeterminado de ActivityIdFormat es W3C</span><span class="sxs-lookup"><span data-stu-id="4e877-120">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="4e877-121">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-121">5.0</span></span> |
| [<span data-ttu-id="4e877-122">Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="4e877-122">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="4e877-123">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-123">5.0</span></span> |
| [<span data-ttu-id="4e877-124">Los métodos CompareGreaterThan de SSE y SSE2 controlan correctamente las entradas NaN</span><span class="sxs-lookup"><span data-stu-id="4e877-124">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="4e877-125">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-125">5.0</span></span> |
| [<span data-ttu-id="4e877-126">CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia</span><span class="sxs-lookup"><span data-stu-id="4e877-126">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="4e877-127">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-127">5.0</span></span> |
| [<span data-ttu-id="4e877-128">Retirada del paquete Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="4e877-128">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="4e877-129">5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-129">5.0</span></span> |
| [<span data-ttu-id="4e877-130">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="4e877-130">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="4e877-131">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-131">3.0</span></span> |
| [<span data-ttu-id="4e877-132">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="4e877-132">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="4e877-133">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-133">3.0</span></span> |
| [<span data-ttu-id="4e877-134">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="4e877-134">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="4e877-135">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-135">3.0</span></span> |
| [<span data-ttu-id="4e877-136">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="4e877-136">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="4e877-137">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-137">3.0</span></span> |
| [<span data-ttu-id="4e877-138">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="4e877-138">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="4e877-139">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-139">3.0</span></span> |
| [<span data-ttu-id="4e877-140">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="4e877-140">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="4e877-141">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-141">3.0</span></span> |
| [<span data-ttu-id="4e877-142">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="4e877-142">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="4e877-143">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-143">3.0</span></span> |
| [<span data-ttu-id="4e877-144">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="4e877-144">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="4e877-145">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-145">3.0</span></span> |
| [<span data-ttu-id="4e877-146">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="4e877-146">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="4e877-147">3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-147">3.0</span></span> |
| [<span data-ttu-id="4e877-148">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="4e877-148">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="4e877-149">2.1</span><span class="sxs-lookup"><span data-stu-id="4e877-149">2.1</span></span> |
| [<span data-ttu-id="4e877-150">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="4e877-150">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="4e877-151">2.1</span><span class="sxs-lookup"><span data-stu-id="4e877-151">2.1</span></span> |
| [<span data-ttu-id="4e877-152">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="4e877-152">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="4e877-153">2.1</span><span class="sxs-lookup"><span data-stu-id="4e877-153">2.1</span></span> |
| [<span data-ttu-id="4e877-154">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="4e877-154">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="4e877-155">1.0</span><span class="sxs-lookup"><span data-stu-id="4e877-155">1.0</span></span> |
| [<span data-ttu-id="4e877-156">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="4e877-156">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="4e877-157">1.0</span><span class="sxs-lookup"><span data-stu-id="4e877-157">1.0</span></span> |
| [<span data-ttu-id="4e877-158">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="4e877-158">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="4e877-159">1.0</span><span class="sxs-lookup"><span data-stu-id="4e877-159">1.0</span></span> |
| [<span data-ttu-id="4e877-160">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="4e877-160">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="4e877-161">1.0</span><span class="sxs-lookup"><span data-stu-id="4e877-161">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="4e877-162">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4e877-162">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="4e877-163">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4e877-163">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="4e877-164">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4e877-164">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="4e877-165">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4e877-165">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
