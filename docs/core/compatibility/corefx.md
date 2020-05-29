---
title: Cambios importantes de la biblioteca de clases base
description: Muestra los cambios importantes en las bibliotecas básicas de .NET.
ms.date: 09/20/2019
ms.openlocfilehash: ca50123b842c256607d47010dbef9b216ece4661
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420439"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="85d3c-103">Cambios importantes en las bibliotecas principales de .NET</span><span class="sxs-lookup"><span data-stu-id="85d3c-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="85d3c-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="85d3c-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="85d3c-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="85d3c-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="85d3c-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="85d3c-106">Breaking change</span></span> | <span data-ttu-id="85d3c-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="85d3c-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="85d3c-108">Los métodos CompareGreaterThan de SSE y SSE2 controlan correctamente las entradas NaN</span><span class="sxs-lookup"><span data-stu-id="85d3c-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="85d3c-109">5.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-109">5.0</span></span> |
| [<span data-ttu-id="85d3c-110">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="85d3c-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="85d3c-111">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-111">3.0</span></span> |
| [<span data-ttu-id="85d3c-112">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="85d3c-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="85d3c-113">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-113">3.0</span></span> |
| [<span data-ttu-id="85d3c-114">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="85d3c-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="85d3c-115">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-115">3.0</span></span> |
| [<span data-ttu-id="85d3c-116">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="85d3c-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="85d3c-117">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-117">3.0</span></span> |
| [<span data-ttu-id="85d3c-118">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="85d3c-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="85d3c-119">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-119">3.0</span></span> |
| [<span data-ttu-id="85d3c-120">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="85d3c-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="85d3c-121">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-121">3.0</span></span> |
| [<span data-ttu-id="85d3c-122">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="85d3c-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="85d3c-123">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-123">3.0</span></span> |
| [<span data-ttu-id="85d3c-124">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="85d3c-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="85d3c-125">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-125">3.0</span></span> |
| [<span data-ttu-id="85d3c-126">Tipo de excepción del serializador JSON cambiado de JsonException a NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="85d3c-126">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="85d3c-127">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-127">3.0</span></span> |
| [<span data-ttu-id="85d3c-128">Cambio en la semántica de (string)null en Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="85d3c-128">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="85d3c-129">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-129">3.0</span></span> |
| [<span data-ttu-id="85d3c-130">Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional</span><span class="sxs-lookup"><span data-stu-id="85d3c-130">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="85d3c-131">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-131">3.0</span></span> |
| [<span data-ttu-id="85d3c-132">Ha cambiado la firma de JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="85d3c-132">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="85d3c-133">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-133">3.0</span></span> |
| [<span data-ttu-id="85d3c-134">Cambios en la API de JsonElement</span><span class="sxs-lookup"><span data-stu-id="85d3c-134">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="85d3c-135">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-135">3.0</span></span> |
| [<span data-ttu-id="85d3c-136">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="85d3c-136">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="85d3c-137">3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-137">3.0</span></span> |
| [<span data-ttu-id="85d3c-138">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="85d3c-138">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="85d3c-139">2.1</span><span class="sxs-lookup"><span data-stu-id="85d3c-139">2.1</span></span> |
| [<span data-ttu-id="85d3c-140">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="85d3c-140">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="85d3c-141">2.1</span><span class="sxs-lookup"><span data-stu-id="85d3c-141">2.1</span></span> |
| [<span data-ttu-id="85d3c-142">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="85d3c-142">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="85d3c-143">2.1</span><span class="sxs-lookup"><span data-stu-id="85d3c-143">2.1</span></span> |
| [<span data-ttu-id="85d3c-144">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="85d3c-144">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="85d3c-145">1.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-145">1.0</span></span> |
| [<span data-ttu-id="85d3c-146">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="85d3c-146">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="85d3c-147">1.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-147">1.0</span></span> |
| [<span data-ttu-id="85d3c-148">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="85d3c-148">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="85d3c-149">1.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-149">1.0</span></span> |
| [<span data-ttu-id="85d3c-150">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="85d3c-150">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="85d3c-151">1.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-151">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="85d3c-152">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-152">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="85d3c-153">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-153">.NET Core 3.0</span></span>

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

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

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

## <a name="net-core-21"></a><span data-ttu-id="85d3c-154">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="85d3c-154">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="85d3c-155">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="85d3c-155">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
