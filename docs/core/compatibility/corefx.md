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
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a>Cambios importantes en las bibliotecas básicas de .NET en .NET Core 1.0-3.0

Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | :-: |
| [Las API que notifican la versión ahora notifican la versión del producto y no la del archivo](#apis-that-report-version-now-report-product-and-not-file-version) | 3.0 |
| [Las instancias personalizadas de EncoderFallbackBuffer no pueden retroceder de forma recursiva](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | 3.0 |
| [Cambios en el comportamientos de formato y análisis de punto flotante](#floating-point-formatting-and-parsing-behavior-changed) | 3.0 |
| [Las operaciones de análisis de punto flotante ya no producen un error ni una excepción OverflowException](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | 3.0 |
| [Se ha movido InvalidAsynchronousStateException a otro ensamblado](#invalidasynchronousstateexception-moved-to-another-assembly) | 3.0 |
| [Al reemplazar las secuencias de bytes UTF-8 con formato incorrecto se siguen las instrucciones de Unicode](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | 3.0 |
| [Se ha movido TypeDescriptionProviderAttribute a otro ensamblado](#typedescriptionproviderattribute-moved-to-another-assembly) | 3.0 |
| [ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | 3.0 |
| [FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | 3.0 |
| [Se han agregado campos privados a tipos struct integrados](#private-fields-added-to-built-in-struct-types) | 2.1 |
| [Cambio del valor predeterminado de UseShellExecute](#change-in-default-value-of-useshellexecute) | 2.1 |
| [Versiones de OpenSSL en macOS](#openssl-versions-on-macos) | 2.1 |
| [UnauthorizedAccessException producida por FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | 1.0 |
| [No se admite el control de excepciones de estado de proceso dañado](#handling-corrupted-state-exceptions-is-not-supported) | 1.0 |
| [Las propiedades UriBuilder ya no anteponen caracteres iniciales](#uribuilder-properties-no-longer-prepend-leading-characters) | 1.0 |
| [Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | 1.0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

**_

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

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

_**
