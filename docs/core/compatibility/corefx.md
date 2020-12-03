---
title: Cambios importantes de las bibliotecas de .NET
description: Se enumeran los cambios importantes en las bibliotecas básicas de .NET para las versiones 1.0-3.0 de .NET Core.
ms.date: 07/27/2020
ms.openlocfilehash: 0f42429e44776fc70bb99ed3bdf346f0d5dbc9eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "96032048"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a><span data-ttu-id="a84d9-103">Cambios importantes en las bibliotecas básicas de .NET en .NET Core 1.0-3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-103">Core .NET libraries breaking changes in .NET Core 1.0-3.0</span></span>

<span data-ttu-id="a84d9-104">Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a84d9-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="a84d9-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="a84d9-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a84d9-106">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="a84d9-106">Breaking change</span></span> | <span data-ttu-id="a84d9-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a84d9-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a84d9-108">Las API que notifican la versión ahora notifican la versión del producto y no la del archivo</span><span class="sxs-lookup"><span data-stu-id="a84d9-108">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="a84d9-109">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-109">3.0</span></span> |
| [<span data-ttu-id="a84d9-110">Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="a84d9-110">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="a84d9-111">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-111">3.0</span></span> |
| [<span data-ttu-id="a84d9-112">Cambios en el comportamientos de formato y análisis de punto flotante</span><span class="sxs-lookup"><span data-stu-id="a84d9-112">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="a84d9-113">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-113">3.0</span></span> |
| [<span data-ttu-id="a84d9-114">Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="a84d9-114">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="a84d9-115">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-115">3.0</span></span> |
| [<span data-ttu-id="a84d9-116">Se ha movido InvalidAsynchronousStateException a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="a84d9-116">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="a84d9-117">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-117">3.0</span></span> |
| [<span data-ttu-id="a84d9-118">Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode</span><span class="sxs-lookup"><span data-stu-id="a84d9-118">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="a84d9-119">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-119">3.0</span></span> |
| [<span data-ttu-id="a84d9-120">Se ha movido TypeDescriptionProviderAttribute a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="a84d9-120">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="a84d9-121">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-121">3.0</span></span> |
| [<span data-ttu-id="a84d9-122">ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes</span><span class="sxs-lookup"><span data-stu-id="a84d9-122">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="a84d9-123">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-123">3.0</span></span> |
| [<span data-ttu-id="a84d9-124">FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="a84d9-124">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="a84d9-125">3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-125">3.0</span></span> |
| [<span data-ttu-id="a84d9-126">Se han agregado campos privados a tipos struct integrados</span><span class="sxs-lookup"><span data-stu-id="a84d9-126">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="a84d9-127">2.1</span><span class="sxs-lookup"><span data-stu-id="a84d9-127">2.1</span></span> |
| [<span data-ttu-id="a84d9-128">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="a84d9-128">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="a84d9-129">2.1</span><span class="sxs-lookup"><span data-stu-id="a84d9-129">2.1</span></span> |
| [<span data-ttu-id="a84d9-130">Versiones de OpenSSL en macOS</span><span class="sxs-lookup"><span data-stu-id="a84d9-130">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="a84d9-131">2.1</span><span class="sxs-lookup"><span data-stu-id="a84d9-131">2.1</span></span> |
| [<span data-ttu-id="a84d9-132">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="a84d9-132">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="a84d9-133">1.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-133">1.0</span></span> |
| [<span data-ttu-id="a84d9-134">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="a84d9-134">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="a84d9-135">1.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-135">1.0</span></span> |
| [<span data-ttu-id="a84d9-136">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="a84d9-136">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="a84d9-137">1.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-137">1.0</span></span> |
| [<span data-ttu-id="a84d9-138">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="a84d9-138">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="a84d9-139">1.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-139">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="a84d9-140">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-140">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

<span data-ttu-id="a84d9-141">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a84d9-141">\*\*_</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="a84d9-142">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a84d9-142">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="a84d9-143">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="a84d9-143">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="a84d9-144">_\*\*</span><span class="sxs-lookup"><span data-stu-id="a84d9-144">_\*\*</span></span>
