---
title: Cambios importantes de las bibliotecas de .NET
description: Se enumeran los cambios importantes en las bibliotecas básicas de .NET para las versiones 1.0-3.0 de .NET Core.
ms.date: 07/27/2020
ms.openlocfilehash: 092ff36a5e07c9e226fe2a67d5e7cfd391e9d16b
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366863"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a><span data-ttu-id="5c0dc-103">Cambios importantes en las bibliotecas básicas de .NET en .NET Core 1.0-3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-103">Core .NET libraries breaking changes in .NET Core 1.0-3.0</span></span>

<span data-ttu-id="5c0dc-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c0dc-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="5c0dc-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="5c0dc-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="5c0dc-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="5c0dc-106">Breaking change</span></span> | <span data-ttu-id="5c0dc-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5c0dc-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="5c0dc-108">El paso de GroupCollection a métodos de extensión que toman IEnumerable\<T> requiere desambiguación</span><span class="sxs-lookup"><span data-stu-id="5c0dc-108">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>](#passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation) | <span data-ttu-id="5c0dc-109">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-109">3.0</span></span> |
| [<span data-ttu-id="5c0dc-110">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="5c0dc-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="5c0dc-111">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-111">3.0</span></span> |
| [<span data-ttu-id="5c0dc-112">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="5c0dc-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="5c0dc-113">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-113">3.0</span></span> |
| [<span data-ttu-id="5c0dc-114">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="5c0dc-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="5c0dc-115">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-115">3.0</span></span> |
| [<span data-ttu-id="5c0dc-116">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="5c0dc-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="5c0dc-117">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-117">3.0</span></span> |
| [<span data-ttu-id="5c0dc-118">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="5c0dc-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="5c0dc-119">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-119">3.0</span></span> |
| [<span data-ttu-id="5c0dc-120">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="5c0dc-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="5c0dc-121">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-121">3.0</span></span> |
| [<span data-ttu-id="5c0dc-122">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="5c0dc-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="5c0dc-123">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-123">3.0</span></span> |
| [<span data-ttu-id="5c0dc-124">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="5c0dc-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="5c0dc-125">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-125">3.0</span></span> |
| [<span data-ttu-id="5c0dc-126">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="5c0dc-126">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="5c0dc-127">3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-127">3.0</span></span> |
| [<span data-ttu-id="5c0dc-128">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="5c0dc-128">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="5c0dc-129">2.1</span><span class="sxs-lookup"><span data-stu-id="5c0dc-129">2.1</span></span> |
| [<span data-ttu-id="5c0dc-130">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="5c0dc-130">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="5c0dc-131">2.1</span><span class="sxs-lookup"><span data-stu-id="5c0dc-131">2.1</span></span> |
| [<span data-ttu-id="5c0dc-132">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="5c0dc-132">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="5c0dc-133">2.1</span><span class="sxs-lookup"><span data-stu-id="5c0dc-133">2.1</span></span> |
| [<span data-ttu-id="5c0dc-134">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="5c0dc-134">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="5c0dc-135">1.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-135">1.0</span></span> |
| [<span data-ttu-id="5c0dc-136">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="5c0dc-136">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="5c0dc-137">1.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-137">1.0</span></span> |
| [<span data-ttu-id="5c0dc-138">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="5c0dc-138">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="5c0dc-139">1.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-139">1.0</span></span> |
| [<span data-ttu-id="5c0dc-140">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="5c0dc-140">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="5c0dc-141">1.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-141">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="5c0dc-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-142">.NET Core 3.0</span></span>

[!INCLUDE [disambiguate-generic-type-for-groupcollection](../../../includes/core-changes/corefx/3.0/disambiguate-generic-type-for-groupcollection.md)]

***

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

<span data-ttu-id="5c0dc-143">\*\*_</span><span class="sxs-lookup"><span data-stu-id="5c0dc-143">\*\*_</span></span>

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

_*_

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="5c0dc-144">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5c0dc-144">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="5c0dc-145">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="5c0dc-145">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="5c0dc-146">_\*\*</span><span class="sxs-lookup"><span data-stu-id="5c0dc-146">_\*\*</span></span>
