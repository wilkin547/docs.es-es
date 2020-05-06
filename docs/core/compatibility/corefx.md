---
title: Cambios importantes de la biblioteca de clases base
description: Muestra los cambios importantes en las bibliotecas básicas de .NET.
ms.date: 09/20/2019
ms.openlocfilehash: 3356017ee49e7cd42e40234ea2c637fe85db7d71
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595693"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="b5b17-103">Cambios importantes en las bibliotecas principales de .NET</span><span class="sxs-lookup"><span data-stu-id="b5b17-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="b5b17-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b5b17-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="b5b17-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="b5b17-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="b5b17-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="b5b17-106">Breaking change</span></span> | <span data-ttu-id="b5b17-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b5b17-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="b5b17-108">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="b5b17-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="b5b17-109">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-109">3.0</span></span> |
| [<span data-ttu-id="b5b17-110">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="b5b17-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="b5b17-111">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-111">3.0</span></span> |
| [<span data-ttu-id="b5b17-112">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="b5b17-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="b5b17-113">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-113">3.0</span></span> |
| [<span data-ttu-id="b5b17-114">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="b5b17-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="b5b17-115">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-115">3.0</span></span> |
| [<span data-ttu-id="b5b17-116">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="b5b17-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="b5b17-117">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-117">3.0</span></span> |
| [<span data-ttu-id="b5b17-118">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="b5b17-118">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="b5b17-119">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-119">3.0</span></span> |
| [<span data-ttu-id="b5b17-120">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="b5b17-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="b5b17-121">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-121">3.0</span></span> |
| [<span data-ttu-id="b5b17-122">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="b5b17-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="b5b17-123">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-123">3.0</span></span> |
| [<span data-ttu-id="b5b17-124">Tipo de excepción del serializador JSON cambiado de JsonException a NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="b5b17-124">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="b5b17-125">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-125">3.0</span></span> |
| [<span data-ttu-id="b5b17-126">Cambio en la semántica de (string)null en Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="b5b17-126">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="b5b17-127">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-127">3.0</span></span> |
| [<span data-ttu-id="b5b17-128">Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional</span><span class="sxs-lookup"><span data-stu-id="b5b17-128">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="b5b17-129">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-129">3.0</span></span> |
| [<span data-ttu-id="b5b17-130">Ha cambiado la firma de JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="b5b17-130">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="b5b17-131">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-131">3.0</span></span> |
| [<span data-ttu-id="b5b17-132">Cambios en la API de JsonElement</span><span class="sxs-lookup"><span data-stu-id="b5b17-132">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="b5b17-133">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-133">3.0</span></span> |
| [<span data-ttu-id="b5b17-134">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="b5b17-134">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="b5b17-135">3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-135">3.0</span></span> |
| [<span data-ttu-id="b5b17-136">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="b5b17-136">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="b5b17-137">2.1</span><span class="sxs-lookup"><span data-stu-id="b5b17-137">2.1</span></span> |
| [<span data-ttu-id="b5b17-138">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="b5b17-138">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="b5b17-139">2.1</span><span class="sxs-lookup"><span data-stu-id="b5b17-139">2.1</span></span> |
| [<span data-ttu-id="b5b17-140">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="b5b17-140">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="b5b17-141">2.1</span><span class="sxs-lookup"><span data-stu-id="b5b17-141">2.1</span></span> |
| [<span data-ttu-id="b5b17-142">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="b5b17-142">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="b5b17-143">1.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-143">1.0</span></span> |
| [<span data-ttu-id="b5b17-144">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="b5b17-144">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="b5b17-145">1.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-145">1.0</span></span> |
| [<span data-ttu-id="b5b17-146">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="b5b17-146">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="b5b17-147">1.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-147">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="b5b17-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-148">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="b5b17-149">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b5b17-149">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="b5b17-150">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="b5b17-150">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***
