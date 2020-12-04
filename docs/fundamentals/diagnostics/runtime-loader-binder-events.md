---
title: Eventos de tiempo de ejecución del cargador y del enlazador
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica de los eventos ETW del cargador y del enlazador, que recopilan información sobre el cargador y el enlazador de ensamblados.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Assembly Loader events (CoreCLR)
- Assembly Binder events (CoreCLR)
- ETW, EventPipe, LTTng assembly loader and binder events (CoreCLR)
ms.openlocfilehash: 2284c580482f6b93a77f44649225ff7e5485666a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594725"
---
# <a name="net-runtime-loader-and-binder-events"></a>Cargador de tiempo de ejecución de .NET y eventos del enlazador

Estos eventos recopilan información relacionada con la carga y descarga de ensamblados y módulos. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`DomainModuleLoad_V1`|151|Se genera cuando se carga un módulo para un dominio de aplicación.|

## <a name="moduleload_v2-event"></a>Evento ModuleLoad_V2

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ModuleLoad_V2`|152|Se genera cuando se carga un módulo durante la duración de un proceso.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Identificador único para el módulo.|
|`AssemblyID`|`win:UInt64`|Identificador del ensamblado en el que reside este módulo.|
|`ModuleFlags`|`win:UInt32`|0x1: módulo neutro de dominio.<br /><br /> 0x2: módulo con una imagen nativa.<br /><br /> 0x4: módulo dinámico.<br /><br /> 0x8: módulo de manifiesto.|
|`Reserved1`|`win:UInt32`|Campo reservado.|
|`ModuleILPath`|`win:UnicodeString`|Ruta de acceso de la imagen de lenguaje intermedio común (CIL) para el módulo, o nombre de módulo dinámico si es un ensamblado dinámico (terminado en null).|
|`ModuleNativePath`|`win:UnicodeString`|Ruta de acceso de la imagen nativa de módulo, si está presente (terminado en null).|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Firma GUID de la base de datos de programa (PDB) administrada que coincide con este módulo.|
|`ManagedPdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB administrada que coincide con este módulo.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB administrada que coincide con este módulo. En algunos casos, puede tratarse simplemente de un nombre de archivo.|
|`NativePdbSignature`|`win:GUID`|Firma GUID del PDB del generador de imágenes nativas (NGen) que coincide con este módulo, en su caso.|
|`NativePdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB de NGen que coincide con este módulo, en su caso.|
|`NativePdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB de NGen que coincide con este módulo, en su caso. En algunos casos, puede tratarse simplemente de un nombre de archivo.|

## <a name="moduleunload_v2-event"></a>Evento ModuleUnload_V2

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ModuleUnload_V2`|153|Se genera cuando se descarga un módulo durante la duración de un proceso.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Identificador único para el módulo.|
|`AssemblyID`|`win:UInt64`|Identificador del ensamblado en el que reside este módulo.|
|`ModuleFlags`|`win:UInt32`|0x1: módulo neutro de dominio.<br /><br /> 0x2: módulo con una imagen nativa.<br /><br /> 0x4: módulo dinámico.<br /><br /> 0x8: módulo de manifiesto.|
|`Reserved1`|`win:UInt32`|Campo reservado.|
|`ModuleILPath`|`win:UnicodeString`|Ruta de acceso de la imagen de lenguaje intermedio común (CIL) para el módulo, o nombre de módulo dinámico si es un ensamblado dinámico (terminado en null).|
|`ModuleNativePath`|`win:UnicodeString`|Ruta de acceso de la imagen nativa de módulo, si está presente (terminado en null).|
|`ClrInstanceID`|``win:UInt16``|Identificador único para la instancia de CLR o CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Firma GUID de la base de datos de programa (PDB) administrada que coincide con este módulo.|
|`ManagedPdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB administrada que coincide con este módulo.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB administrada que coincide con este módulo. En algunos casos, puede tratarse simplemente de un nombre de archivo.|
|`NativePdbSignature`|`win:GUID`|Firma GUID del PDB del generador de imágenes nativas (NGen) que coincide con este módulo, en su caso.|
|`NativePdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB de NGen que coincide con este módulo, en su caso.|
|`NativePdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB de NGen que coincide con este módulo, en su caso. En algunos casos, puede tratarse simplemente de un nombre de archivo.|

## <a name="moduledcstart_v2-event"></a>Evento ModuleDCStart_V2

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)

|Evento|Id. de evento|Descripción
|-----------|--------------|-----------------|
|`ModuleDCStart_V2`|153|Enumera los módulos durante una detención de inicio.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Identificador único para el módulo.|
|`AssemblyID`|`win:UInt64`|Identificador del ensamblado en el que reside este módulo.|
|`ModuleFlags`|`win:UInt32`|0x1: módulo neutro de dominio.<br /><br /> 0x2: módulo con una imagen nativa.<br /><br /> 0x4: módulo dinámico.<br /><br /> 0x8: módulo de manifiesto.|
|`Reserved1`|`win:UInt32`|Campo reservado.|
|`ModuleILPath`|`win:UnicodeString`|Ruta de acceso de la imagen de lenguaje intermedio común (CIL) para el módulo, o nombre de módulo dinámico si es un ensamblado dinámico (terminado en null).|
|`ModuleNativePath`|`win:UnicodeString`|Ruta de acceso de la imagen nativa de módulo, si está presente (terminado en null).|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Firma GUID de la base de datos de programa (PDB) administrada que coincide con este módulo.|
|`ManagedPdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB administrada que coincide con este módulo.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB administrada que coincide con este módulo. En algunos casos, puede tratarse simplemente de un nombre de archivo.|
|`NativePdbSignature`|`win:GUID`|Firma GUID del PDB del generador de imágenes nativas (NGen) que coincide con este módulo, en su caso.|
|`NativePdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB de NGen que coincide con este módulo, en su caso.|
|`NativePdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB de NGen que coincide con este módulo, en su caso. En algunos casos, puede tratarse simplemente de un nombre de archivo.|

## <a name="moduledcend_v2-event"></a>Evento ModuleDCEnd_V2

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ModuleDCEnd_V2`|154|Enumera los módulos durante una detención de finalización.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Identificador único para el módulo.|
|`AssemblyID`|`win:UInt64`|Identificador del ensamblado en el que reside este módulo.|
|`ModuleFlags`|`win:UInt32`|0x1: módulo neutro de dominio.<br /><br /> 0x2: módulo con una imagen nativa.<br /><br /> 0x4: módulo dinámico.<br /><br /> 0x8: módulo de manifiesto.|
|`Reserved1`|`win:UInt32`|Campo reservado.|
|`ModuleILPath`|`win:UnicodeString`|Ruta de acceso de la imagen de lenguaje intermedio común (CIL) para el módulo, o nombre de módulo dinámico si es un ensamblado dinámico (terminado en null).|
|`ModuleNativePath`|`win:UnicodeString`|Ruta de acceso de la imagen nativa de módulo, si está presente (terminado en null).|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Firma GUID de la base de datos de programa (PDB) administrada que coincide con este módulo.|
|`ManagedPdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB administrada que coincide con este módulo.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB administrada que coincide con este módulo. En algunos casos, puede tratarse simplemente de un nombre de archivo.|
|`NativePdbSignature`|`win:GUID`|Firma GUID del PDB del generador de imágenes nativas (NGen) que coincide con este módulo, en su caso.|
|`NativePdbAge`|`win:UInt32`|Número de antigüedad escrito en la PDB de NGen que coincide con este módulo, en su caso.|
|`NativePdbBuildPath`|`win:UnicodeString`|Ruta de acceso a la ubicación donde se creó la PDB de NGen que coincide con este módulo, en su caso. En algunos casos, puede tratarse simplemente de un nombre de archivo.|

## <a name="assemblyload_v1-event"></a>Evento AssemblyLoad_V1

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AssemblyLoad_V1`|154|Se genera cuando se carga un ensamblado.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|Identificador único para el ensamblado.|
|`AppDomainID`|`win:UInt64`|Identificador del dominio de este ensamblado.|
|`BindingID`|`win:UInt64`|Identificador que identifica de forma exclusiva el enlace de ensamblado.|
|`AssemblyFlags`|`win:UInt32`|0x1: ensamblado neutro de dominio.<br /><br /> 0x2: ensamblado dinámico.<br /><br /> 0x4: ensamblado con una imagen nativa.<br /><br /> 0x8: ensamblado recopilable.|
|`AssemblyName`|`win:UnicodeString`|Nombre completo del ensamblado.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.

## <a name="assemblyunload_v1-event"></a>Evento AssemblyUnload_V1

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`FireAssemblyUnload_V1`|155|Se genera cuando se carga un ensamblado.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|Identificador único para el ensamblado.|
|`AppDomainID`|`win:UInt64`|Identificador del dominio de este ensamblado.|
|`BindingID`|`win:UInt64`|Identificador que identifica de forma exclusiva el enlace de ensamblado.|
|`AssemblyFlags`|`win:UInt32`|0x1: ensamblado neutro de dominio.<br /><br /> 0x2: ensamblado dinámico.<br /><br /> 0x4: ensamblado con una imagen nativa.<br /><br /> 0x8: ensamblado recopilable.|
|`AssemblyName`|`win:UnicodeString`|Nombre completo del ensamblado.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="assemblydcstart_v1-event"></a>Evento AssemblyDCStart_V1

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AssemblyDCStart_V1`|155|Enumera los ensamblados durante una detención de inicio.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|Identificador único para el ensamblado.|
|`AppDomainID`|`win:UInt64`|Identificador del dominio de este ensamblado.|
|`BindingID`|`win:UInt64`|Identificador que identifica de forma exclusiva el enlace de ensamblado.|
|`AssemblyFlags`|`win:UInt32`|0x1: ensamblado neutro de dominio.<br /><br /> 0x2: ensamblado dinámico.<br /><br /> 0x4: ensamblado con una imagen nativa.<br /><br /> 0x8: ensamblado recopilable.|
|`AssemblyName`|`win:UnicodeString`|Nombre completo del ensamblado.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="assemblyloadstart-event"></a>Evento AssemblyLoadStart

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|`AssemblyLoadStart`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|290|Se ha solicitado una carga de ensamblado.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Nombre del nombre del ensamblado.|
|`AssemblyPath`|`win:UnicodeString`|Ruta de acceso del nombre del ensamblado.|
|`RequestingAssembly`|`win:UnicodeString`|Nombre del ensamblado que solicita ("primario").|
|`AssemblyLoadContext`|`win:UnicodeString`|Contexto de carga del ensamblado.|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|Contexto de carga del ensamblado de solicitud ("primario").|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="assemblyloadstop-event"></a>Evento AssemblyLoadStop

|Palabra clave para generar el evento|Evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|`AssemblyLoadStart`|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|291|Se ha solicitado una carga de ensamblado.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Nombre del nombre del ensamblado.|
|`AssemblyPath`|`win:UnicodeString`|Ruta de acceso del nombre del ensamblado.|
|`RequestingAssembly`|`win:UnicodeString`|Nombre del ensamblado que solicita ("primario").|
|`AssemblyLoadContext`|`win:UnicodeString`|Contexto de carga del ensamblado.|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|Contexto de carga del ensamblado de solicitud ("primario").|
|`Success`|`win:Boolean`|Si la carga del ensamblado se realizó correctamente.|
|`ResultAssemblyName`|`win:UnicodeString`|Nombre del ensamblado que se cargó.|
|`ResultAssemblyPath`|`win:UnicodeString`|Ruta de acceso del ensamblado que se cargó desde.|
|`Cached`|`win:UnicodeString`|Indica si la carga se almacenó en caché.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="resolutionattempted-event"></a>Evento ResolutionAttempted

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`ResolutionAttempted`|292|Se ha solicitado una carga de ensamblado.

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Nombre del nombre del ensamblado.|
|`Stage`|`win:UInt16`|La fase de resolución.<br/><br/>0: buscar en la carga.<br/><br/>1: contexto de carga de ensamblado</br><br/>2: ensamblados de la aplicación.<br/><br/>3: Reserva de contexto de carga de ensamblado predeterminada. <br/><br/>4: resolución del ensamblado satélite. <br/><br/>5: resolución del contexto de carga de ensamblado.<br/><br/>6: resolución de ensamblados de AppDomain.
|`AssemblyLoadContext`|`win:UnicodeString`|Contexto de carga del ensamblado.|
|`Result`|`win:UInt16`|Resultado del intento de resolución.<br/><br/>0: correcto<br/><br/>1: ensamblado NotFound<br/><br/>2: versión incompatible<br/><br/>3: nombre de ensamblado no coincidente<br/><br/>4: error<br/><br/>5: excepción|
|`ResultAssemblyName`|`win:UnicodeString`|Nombre del ensamblado que se resolvió.|
|`ResultAssemblyPath`|`win:UnicodeString`|Ruta de acceso del ensamblado que se resolvió a partir de.|
|`ErrorMessage`|`win:UnicodeString`|Mensaje de error si hay una excepción.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="assemblyloadcontextresolvinghandlerinvoked-event"></a>Evento AssemblyLoadContextResolvingHandlerInvoked

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AssemblyLoadContextResolvingHandlerInvoked`|293|Se ha invocado un controlador de [AssemblyLoadContext. resolviendo](xref:System.Runtime.Loader.AssemblyLoadContext.Resolving) .|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Nombre del nombre del ensamblado.|
|`HandlerName`|`win:UnicodeString`|Nombre del controlador invocado.|
|`AssemblyLoadContext`|`win:UnicodeString`|Contexto de carga del ensamblado.|
|`ResultAssemblyName`|`win:UnicodeString`|Nombre del ensamblado que se resolvió.|
|`ResultAssemblyPath`|`win:UnicodeString`|Ruta de acceso del ensamblado que se resolvió a partir de.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="appdomainassemblyresolvehandlerinvoked-event"></a>Evento AppDomainAssemblyResolveHandlerInvoked

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AppDomainAssemblyResolveHandlerInvoked`|294|Se ha <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> invocado un controlador.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Nombre del nombre del ensamblado.|
|`HandlerName`|`win:UnicodeString`|Nombre del controlador invocado.|
|`ResultAssemblyName`|`win:UnicodeString`|Nombre del ensamblado que se resolvió.|
|`ResultAssemblyPath`|`win:UnicodeString`|Ruta de acceso del ensamblado que se resolvió a partir de.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="assemblyloadfromresolvehandlerinvoked-event"></a>Evento AssemblyLoadFromResolveHandlerInvoked

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`AssemblyLoadFromResolveHandlerInvoked`|295|Se ha <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> invocado un controlador.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Nombre del nombre del ensamblado.|
|`IsTrackedLoad`|`win:Boolean`|Indica si se realiza un seguimiento de la carga del ensamblado.|
|`RequestingAssemblyPath`|`win:UnicodeString`|Ruta de acceso del ensamblado que se solicita.|
|`ComputedRequestedAssemblyPath`|`win:UnicodeString`|Ruta de acceso del ensamblado que se solicitó.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|

## <a name="knownpathprobed-event"></a>Evento KnownPathProbed

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Informativo (4)|

|Evento|Id. de evento|Descripción|
|-----------|--------------|-----------------|
|`KnownPathProbed`|296|Se sondeó una ruta de acceso conocida para un ensamblado.|

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|`FilePath`|`win:UnicodeString`|Ruta de acceso sondeada.|
|`Source`|`win:UInt16`|Origen de la ruta de acceso sondeada.<br/><br/>0X0: ensamblados de aplicación.<br/><br/>0x1: ruta de acceso de imagen nativa de la aplicación.<br/><br/>0X2: ruta de acceso de la aplicación.</br><br/>0X3: raíces de recursos de la plataforma.<br/><br/>0x4: subdirectorio satélite.</br>|
|`Result`|`win:UInt32`|HRESULT para el sondeo.|
|`ClrInstanceID`|`win:UInt16`|IDENTIFICADOR único de la instancia de CoreCLR.|
