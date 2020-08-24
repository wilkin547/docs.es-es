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
# <a name="core-net-libraries-breaking-changes"></a>Cambios importantes en las bibliotecas principales de .NET

Las bibliotecas principales de .NET proporcionan los tipos primitivos y otros tipos generales que usa .NET Core.

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | :-: |
| [Aumento de la complejidad de LINQ OrderBy.First{OrDefault}](#complexity-of-linq-orderbyfirstordefault-increased) | 5.0 |
| [IntPtr y UIntPtr implementan IFormattable](#intptr-and-uintptr-implement-iformattable) | 5.0 |
| [PrincipalPermissionAttribute está obsoleto como error](#principalpermissionattribute-is-obsolete-as-error) | 5.0 |
| [Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | 5.0 |
| [Las rutas de acceso al código UTF-7 están obsoletas](#utf-7-code-paths-are-obsolete) | 5.0 |
| [Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos](#vectort-always-throws-notsupportedexception-for-unsupported-types) | 5.0 |
| [El valor predeterminado de ActivityIdFormat es W3C](#default-activityidformat-is-w3c) | 5.0 |
| [Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp](#behavior-change-for-vector2lerp-and-vector4lerp) | 5.0 |
| [Los métodos CompareGreaterThan de SSE y SSE2 controlan correctamente las entradas NaN](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | 5.0 |
| [CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | 5.0 |
| [Retirada del paquete Microsoft.DotNet.PlatformAbstractions](#microsoftdotnetplatformabstractions-package-removed) | 5.0 |
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

## <a name="net-50"></a>.NET 5.0

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

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
