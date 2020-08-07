---
title: Cambios importantes de la biblioteca de clases base
description: Muestra los cambios importantes en las bibliotecas básicas de .NET.
ms.date: 07/27/2020
ms.openlocfilehash: 558aa1d76831cd15e2028c17d2b0b2e82f64ef9a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517337"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="eed87-103">Cambios importantes en las bibliotecas principales de .NET</span><span class="sxs-lookup"><span data-stu-id="eed87-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="eed87-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="eed87-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="eed87-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="eed87-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="eed87-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="eed87-106">Breaking change</span></span> | <span data-ttu-id="eed87-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="eed87-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="eed87-108">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eed87-108">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="eed87-109">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-109">5.0</span></span> |
| [<span data-ttu-id="eed87-110">Las rutas de acceso al código UTF-7 están obsoletas</span><span class="sxs-lookup"><span data-stu-id="eed87-110">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="eed87-111">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-111">5.0</span></span> |
| [<span data-ttu-id="eed87-112">Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="eed87-112">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="eed87-113">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-113">5.0</span></span> |
| [<span data-ttu-id="eed87-114">El valor predeterminado de ActivityIdFormat es W3C</span><span class="sxs-lookup"><span data-stu-id="eed87-114">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="eed87-115">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-115">5.0</span></span> |
| [<span data-ttu-id="eed87-116">Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="eed87-116">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="eed87-117">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-117">5.0</span></span> |
| [<span data-ttu-id="eed87-118">Los métodos CompareGreaterThan de SSE y SSE2 controlan correctamente las entradas NaN</span><span class="sxs-lookup"><span data-stu-id="eed87-118">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="eed87-119">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-119">5.0</span></span> |
| [<span data-ttu-id="eed87-120">CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia</span><span class="sxs-lookup"><span data-stu-id="eed87-120">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="eed87-121">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-121">5.0</span></span> |
| [<span data-ttu-id="eed87-122">Retirada del paquete Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="eed87-122">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="eed87-123">5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-123">5.0</span></span> |
| [<span data-ttu-id="eed87-124">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="eed87-124">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="eed87-125">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-125">3.0</span></span> |
| [<span data-ttu-id="eed87-126">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="eed87-126">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="eed87-127">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-127">3.0</span></span> |
| [<span data-ttu-id="eed87-128">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="eed87-128">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="eed87-129">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-129">3.0</span></span> |
| [<span data-ttu-id="eed87-130">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="eed87-130">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="eed87-131">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-131">3.0</span></span> |
| [<span data-ttu-id="eed87-132">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="eed87-132">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="eed87-133">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-133">3.0</span></span> |
| [<span data-ttu-id="eed87-134">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="eed87-134">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="eed87-135">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-135">3.0</span></span> |
| [<span data-ttu-id="eed87-136">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="eed87-136">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="eed87-137">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-137">3.0</span></span> |
| [<span data-ttu-id="eed87-138">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="eed87-138">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="eed87-139">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-139">3.0</span></span> |
| [<span data-ttu-id="eed87-140">Cambio en la semántica de (string)null en Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="eed87-140">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="eed87-141">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-141">3.0</span></span> |
| [<span data-ttu-id="eed87-142">Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional</span><span class="sxs-lookup"><span data-stu-id="eed87-142">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="eed87-143">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-143">3.0</span></span> |
| [<span data-ttu-id="eed87-144">Ha cambiado la firma de JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="eed87-144">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="eed87-145">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-145">3.0</span></span> |
| [<span data-ttu-id="eed87-146">Cambios en la API de JsonElement</span><span class="sxs-lookup"><span data-stu-id="eed87-146">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="eed87-147">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-147">3.0</span></span> |
| [<span data-ttu-id="eed87-148">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="eed87-148">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="eed87-149">3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-149">3.0</span></span> |
| [<span data-ttu-id="eed87-150">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="eed87-150">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="eed87-151">2.1</span><span class="sxs-lookup"><span data-stu-id="eed87-151">2.1</span></span> |
| [<span data-ttu-id="eed87-152">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="eed87-152">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="eed87-153">2.1</span><span class="sxs-lookup"><span data-stu-id="eed87-153">2.1</span></span> |
| [<span data-ttu-id="eed87-154">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="eed87-154">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="eed87-155">2.1</span><span class="sxs-lookup"><span data-stu-id="eed87-155">2.1</span></span> |
| [<span data-ttu-id="eed87-156">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="eed87-156">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="eed87-157">1.0</span><span class="sxs-lookup"><span data-stu-id="eed87-157">1.0</span></span> |
| [<span data-ttu-id="eed87-158">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="eed87-158">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="eed87-159">1.0</span><span class="sxs-lookup"><span data-stu-id="eed87-159">1.0</span></span> |
| [<span data-ttu-id="eed87-160">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="eed87-160">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="eed87-161">1.0</span><span class="sxs-lookup"><span data-stu-id="eed87-161">1.0</span></span> |
| [<span data-ttu-id="eed87-162">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="eed87-162">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="eed87-163">1.0</span><span class="sxs-lookup"><span data-stu-id="eed87-163">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="eed87-164">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="eed87-164">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="eed87-165">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="eed87-165">.NET Core 3.0</span></span>

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

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="eed87-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="eed87-166">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="eed87-167">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="eed87-167">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
