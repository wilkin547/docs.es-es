---
title: Cambios importantes de la biblioteca de clases base
description: Enumera los cambios importantes de CoreFx en .NET, la biblioteca de clases base.
ms.date: 09/20/2019
ms.openlocfilehash: 7c59f2a96545e74e4099b6078ff52009740699c6
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449570"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="4445f-103">Cambios importantes de CoreFx</span><span class="sxs-lookup"><span data-stu-id="4445f-103">CoreFx breaking changes</span></span>

<span data-ttu-id="4445f-104">CoreFx proporciona los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4445f-104">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="4445f-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="4445f-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="4445f-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="4445f-106">Breaking change</span></span> | <span data-ttu-id="4445f-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4445f-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="4445f-108">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="4445f-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="4445f-109">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-109">3.0</span></span> |
| [<span data-ttu-id="4445f-110">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="4445f-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="4445f-111">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-111">3.0</span></span> |
| [<span data-ttu-id="4445f-112">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="4445f-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="4445f-113">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-113">3.0</span></span> |
| [<span data-ttu-id="4445f-114">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="4445f-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="4445f-115">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-115">3.0</span></span> |
| [<span data-ttu-id="4445f-116">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="4445f-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="4445f-117">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-117">3.0</span></span> |
| [<span data-ttu-id="4445f-118">.NET Core 3.0 sigue los procedimientos recomendados de Unicode al reemplazar secuencias de bytes UTF-8 con formato incorrecto</span><span class="sxs-lookup"><span data-stu-id="4445f-118">NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences) | <span data-ttu-id="4445f-119">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-119">3.0</span></span> |
| [<span data-ttu-id="4445f-120">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="4445f-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="4445f-121">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-121">3.0</span></span> |
| [<span data-ttu-id="4445f-122">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="4445f-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="4445f-123">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-123">3.0</span></span> |
| [<span data-ttu-id="4445f-124">Tipo de excepción del serializador JSON cambiado de JsonException a NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="4445f-124">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="4445f-125">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-125">3.0</span></span> |
| [<span data-ttu-id="4445f-126">Cambio en la semántica de (string)null en Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="4445f-126">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="4445f-127">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-127">3.0</span></span> |
| [<span data-ttu-id="4445f-128">Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional</span><span class="sxs-lookup"><span data-stu-id="4445f-128">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="4445f-129">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-129">3.0</span></span> |
| [<span data-ttu-id="4445f-130">Ha cambiado la firma de JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="4445f-130">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="4445f-131">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-131">3.0</span></span> |
| [<span data-ttu-id="4445f-132">Cambios en la API de JsonElement</span><span class="sxs-lookup"><span data-stu-id="4445f-132">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="4445f-133">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-133">3.0</span></span> |
| [<span data-ttu-id="4445f-134">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="4445f-134">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="4445f-135">3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-135">3.0</span></span> |
| [<span data-ttu-id="4445f-136">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="4445f-136">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="4445f-137">2.1</span><span class="sxs-lookup"><span data-stu-id="4445f-137">2.1</span></span> |
| [<span data-ttu-id="4445f-138">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="4445f-138">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="4445f-139">2.1</span><span class="sxs-lookup"><span data-stu-id="4445f-139">2.1</span></span> |
| [<span data-ttu-id="4445f-140">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="4445f-140">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="4445f-141">1.0</span><span class="sxs-lookup"><span data-stu-id="4445f-141">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="4445f-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4445f-142">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="4445f-143">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4445f-143">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="4445f-144">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4445f-144">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***
