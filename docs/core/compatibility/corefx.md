---
title: Cambios importantes de la biblioteca de clases base
description: Enumera los cambios importantes de CoreFx en .NET, la biblioteca de clases base.
ms.date: 09/20/2019
ms.openlocfilehash: 9e8a00abfae8bf8f5301a4879cb5274492a2b6fd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093089"
---
# <a name="corefx-breaking-changes"></a>Cambios importantes de CoreFx

CoreFx proporciona los tipos primitivos y otros tipos generales que usa .NET Core.

En esta página se documentan los siguientes cambios importantes:

- [Las API que notifican la versión ahora notifican la versión del producto y no la del archivo](#apis-that-report-version-now-report-product-and-not-file-version)
- [Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively)
- [Cambios en el comportamientos de formato y análisis de punto flotante](#floating-point-formatting-and-parsing-behavior-changed)
- [Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception)
- [Se ha movido InvalidAsynchronousStateException a otro ensamblado](#invalidasynchronousstateexception-moved-to-another-assembly)
- [.NET Core 3.0 sigue los procedimientos recomendados de Unicode al reemplazar secuencias de bytes UTF-8 con formato incorrecto](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences)
- [Se ha movido TypeDescriptionProviderAttribute a otro ensamblado](#typedescriptionproviderattribute-moved-to-another-assembly)
- [ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes)
- [Tipo de excepción del serializador JSON cambiado de JsonException a NotSupportedException](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception)
- [Cambio en la semántica de (string)null en Utf8JsonWriter](#change-in-semantics-of-stringnull-in-utf8jsonwriter)
- [Los métodos JsonEncodedText.Encode tienen un argumento JavaScriptEncoder adicional](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument)
- [Ha cambiado la firma de JsonFactoryConverter.CreateConverter](#jsonfactoryconvertercreateconverter-signature-changed)
- [Cambios en la API de JsonElement](#jsonelement-api-changes)
- [Se han agregado campos privados a tipos struct integrados](#private-fields-added-to-built-in-struct-types)
- [Cambio del valor predeterminado de UseShellExecute](#change-in-default-value-of-useshellexecute)

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="net-core-30-preview-9"></a>.NET Core 3.0 (versión preliminar 9)

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

## <a name="net-core-30-preview-8"></a>.NET Core 3.0 (versión preliminar 8)

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

## <a name="net-core-30-preview-7"></a>.NET Core 3.0 (versión preliminar 7)

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***
