---
title: Eventos ETW de cargador
description: Revise los eventos ETW del cargador, que incluyen eventos de dominio de aplicación, eventos de ensamblado del cargador de CLR, eventos del módulo, eventos del módulo de dominio CLR y eventos de intervalo de módulo.
ms.date: 03/30/2017
helpviewer_keywords:
- loader events [.NET Framework]
- ETW, loader events (CLR)
ms.assetid: cb403cc6-56f8-4609-b467-cdfa09f07909
ms.openlocfilehash: 8220e8e773409be76bc7522d57551f1bddb90e5d
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474363"
---
# <a name="loader-etw-events"></a>Eventos ETW de cargador
Estos eventos recopilan información relativa a la carga y descarga de dominios de aplicación, ensamblados y módulos.  
  
 Todos los eventos de cargador se generan bajo la palabra clave `LoaderKeyword` (0x8). Los eventos `DCStart` y `DCEnd` se generan bajo `LoaderRundownKeyword` (0x8) con `StartRundown`/`EndRundown` habilitado. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  

## <a name="application-domain-events"></a>Eventos de dominio de aplicación
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`AppDomainLoad_V1` y `AppDomainUnLoad_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`AppDomainDCStart_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`AppDomainDCEnd_V1`|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`AppDomainLoad_V1` (registrado para todos los dominios de aplicación)|156|Se genera cuando se crea un dominio de aplicación durante un proceso.|  
|`AppDomainUnLoad_V1`|157|Se genera cuando se destruye un dominio de aplicación durante un proceso.|  
|`AppDomainDCStart_V1`|157|Enumera los dominios de aplicación durante una detención de inicio.|  
|`AppDomainDCEnd_V1`|158|Enumera los dominios de aplicación durante una detención de finalización.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Identificador único de un dominio de aplicación.|  
|AppDomainFlags|win:UInt32|0x1: dominio predeterminado.<br /><br /> 0x2: ejecutable.<br /><br /> 0x4: dominio de aplicación, bit 28-31: directiva de uso compartido de este dominio.<br /><br /> 0: un dominio compartido.|  
|AppDomainName|win:UnicodeString|Nombre descriptivo de dominio de aplicación. Puede cambiar durante la vigencia del proceso.|  
|AppDomainIndex|win:UInt32|Índice de este dominio de aplicación.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  

## <a name="clr-loader-assembly-events"></a>Eventos de ensamblado de cargador CLR  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`AssemblyLoad` y `AssemblyUnload`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`AssemblyDCStart`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`AssemblyDCEnd`|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`AssemblyLoad_V1`|154|Se genera cuando se carga un ensamblado.|  
|`AssemblyUnload_V1`|155|Se genera cuando se descarga un ensamblado.|  
|`AssemblyDCStart_V1`|155|Enumera los ensamblados durante una detención de inicio.|  
|`AssemblyDCEnd_V1`|156|Enumera los ensamblados durante una detención de finalización.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|AssemblyID|win:UInt64|Identificador único para el ensamblado.|  
|AppDomainID|win:UInt64|Identificador del dominio de este ensamblado.|  
|BindingID|win:UInt64|Identificador que identifica de forma exclusiva el enlace de ensamblado.|  
|AssemblyFlags|win:UInt32|0x1: ensamblado neutro de dominio.<br /><br /> 0x2: ensamblado dinámico.<br /><br /> 0x4: ensamblado con una imagen nativa.<br /><br /> 0x8: ensamblado recopilable.|  
|AssemblyName|win:UnicodeString|Nombre completo del ensamblado.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="module-events"></a>Eventos de módulo
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`ModuleLoad_V2` y `ModuleUnload_V2`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`ModuleDCStart_V2`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`ModuleDCEnd_V2`|Informativo (4)|  
||||  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`ModuleLoad_V2`|152|Se genera cuando se carga un módulo durante la duración de un proceso.|  
|`ModuleUnload_V2`|153|Se genera cuando se descarga un módulo durante la duración de un proceso.|  
|`ModuleDCStart_V2`|153|Enumera los módulos durante una detención de inicio.|  
|`ModuleDCEnd_V2`|154|Enumera los módulos durante una detención de finalización.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt64|Identificador único para el módulo.|  
|AssemblyID|win:UInt64|Identificador del ensamblado en el que reside este módulo.|  
|ModuleFlags|win:UInt32|0x1: módulo neutro de dominio.<br /><br /> 0x2: módulo con una imagen nativa.<br /><br /> 0x4: módulo dinámico.<br /><br /> 0x8: módulo de manifiesto.|  
|Reserved1|win:UInt32|Campo reservado.|  
|ModuleILPath|win:UnicodeString|Ruta de acceso de la imagen de lenguaje intermedio de Microsoft (MSIL) para el módulo, o nombre de módulo dinámico si es un ensamblado dinámico (terminado en null).|  
|ModuleNativePath|win:UnicodeString|Ruta de acceso de la imagen nativa de módulo, si está presente (terminado en null).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
|ManagedPdbSignature|win:GUID|Firma GUID de la base de datos de programa (PDB) administrada que coincide con este módulo. (Vea la sección Comentarios).|  
|ManagedPdbAge|win:UInt32|Número de antigüedad escrito en la PDB administrada que coincide con este módulo. (Vea la sección Comentarios).|  
|ManagedPdbBuildPath|win:UnicodeString|Ruta de acceso a la ubicación donde se creó la PDB administrada que coincide con este módulo. En algunos casos, puede tratarse simplemente de un nombre de archivo. (Vea la sección Comentarios).|  
|NativePdbSignature|win:GUID|Firma GUID del PDB del generador de imágenes nativas (NGen) que coincide con este módulo, en su caso. (Vea la sección Comentarios).|  
|NativePdbAge|win:UInt32|Número de antigüedad escrito en la PDB de NGen que coincide con este módulo, en su caso. (Vea la sección Comentarios).|  
|NativePdbBuildPath|win:UnicodeString|Ruta de acceso a la ubicación donde se creó la PDB de NGen que coincide con este módulo, en su caso. En algunos casos, puede tratarse simplemente de un nombre de archivo. (Vea la sección Comentarios).|  
  
### <a name="remarks"></a>Observaciones  
  
- Los campos que tienen “Pdb” en sus nombres pueden ser usados por herramientas de generación de perfiles con el objetivo de buscar las PDB que coincidan con los módulos que se cargaron durante la sesión de generación de perfiles. Los valores de estos campos se corresponden a los datos escritos en las secciones IMAGE_DIRECTORY_ENTRY_DEBUG del módulo usadas normalmente en los depuradores para ayudar a localizar las PDB que coinciden con los módulos cargados.  
  
- Los nombres de campo que empiezan por “ManagedPdb” hacen referencia a la PDB administrada correspondiente al módulo MSIL que generó el compilador administrado (por ejemplo, el compilador de C# o Visual Basic). Esta PDB usa el formato de PDB administrada y describe el modo en que los elementos del código fuente administrado original —como archivos, números de línea y nombres de símbolos— se asignan a los elementos MSIL que se compilan en el módulo MSIL.  
  
- Los nombres de campo que empiezan por “NativePdb” hacen referencia a la PDB de NGen generada al llamar a `NGEN createPDB`. Esta PDB usa el formato de PDB nativa y describe el modo en que los elementos del código fuente administrado original —como archivos, números de línea y nombres de símbolos— se asignan a los elementos nativos que se compilan en el módulo NGen.  

## <a name="clr-domain-module-events"></a>Eventos del módulo de dominio CLR
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`DomainModuleDCStart_V1`|Informativo (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`DomainModuleDCEnd_V1`|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`DomainModuleLoad_V1`|151|Se genera cuando se carga un módulo para un dominio de aplicación.|  
|`DomainModuleDCStart_V1`|151|Enumera los módulos cargados para un dominio de aplicación durante una detención de inicio y se registra para todos los dominios de aplicación.|  
|`DomainModuleDCEnd_V1`|152|Enumera los módulos cargados para un dominio de aplicación durante una detención de finalización y se registra para todos los dominios de aplicación.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt64|Identifica el ensamblado al que pertenece este módulo.|  
|AssemblyID|win:UInt64|Identificador del ensamblado en el que reside este módulo.|  
|AppDomainID|win:UInt64|Identificador del dominio de aplicación en el que se usa este módulo.|  
|ModuleFlags|win:UInt32|0x1: módulo neutro de dominio.<br /><br /> 0x2: módulo con una imagen nativa.<br /><br /> 0x4: módulo dinámico.<br /><br /> 0x8: módulo de manifiesto.|  
|Reserved1|win:UInt32|Campo reservado.|  
|ModuleILPath|win:UnicodeString|Ruta de acceso de la imagen de MSIL para el módulo, o nombre de módulo dinámico si es un ensamblado dinámico (terminado en null).|  
|ModuleNativePath|win:UnicodeString|Ruta de acceso de la imagen nativa de módulo, si está presente (terminado en null).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  

## <a name="module-range-events"></a>Eventos de intervalo de módulo
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`PerfTrackKeyWord`)|`ModuleRange`|Informativo (4)|  
|`PerfTrackKeyWord`|`ModuleRangeDCStart`|Informativo (4)|  
|`PerfTrackKeyWord`|`ModuleRangeDCEnd`|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`ModuleRange`|158|Este evento está presente si una imagen cargada del generador de imágenes nativas (NGen) se ha optimizado con IBC y contiene información sobre las secciones activas de la imagen de NGen.|  
|`ModuleRangeDCStart`|160|Un evento `ModuleRange` se desencadenó al principio de una detención.|  
|`ModuleRangeDCEnd`|161|Un evento `ModuleRange` se desencadenó al final de una detención.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Identifica de forma única una instancia específica de CLR en un proceso si se cargan varias instancias de CLR.|  
|ModuleID|win:UInt64|Identifica el ensamblado al que pertenece este módulo.|  
|RangeBegin|win:UInt32|Desplazamiento en el módulo que representa el inicio del intervalo para el tipo de intervalo especificado.|  
|RangeSize|win:UInt32|Tamaño del intervalo especificado, en bytes.|  
|RangeType|win:UInt32|Un valor único, 0x4, para representar los intervalos fríos de IBC. Este campo puede representar más valores en el futuro.|  
|RangeSize1|win:UInt32|0 indica que los datos son incorrectos.|  
|RangeBegin2|win:UnicodeString||  
  
### <a name="remarks"></a>Observaciones  
 Si una imagen de NGen cargada en un proceso de .NET Framework se optimiza con IBC, el evento `ModuleRange` que contiene los intervalos calientes en la imagen de NGen se registra junto con su `moduleID` y `ClrInstanceID`.  Si la imagen de NGen no está optimizada con IBC, este evento no se registra. Para determinar el nombre del módulo, el evento debe estar intercalado con los eventos ETW de carga de módulo.  
  
 El tamaño de carga para este evento es variable; el campo `Count` indica el número de desplazamientos de intervalo contenido en el evento.  Este evento debe estar intercalado con el evento `IStart` de Windows para determinar los intervalos reales. El evento de carga de imagen de Windows se registra siempre que se carga una imagen y contiene la dirección virtual de la imagen cargada.  
  
 Los eventos del intervalo de módulo se desencadenan en cualquier nivel ETW mayor o igual que 4 y se clasifican como eventos informativos.  
  
## <a name="see-also"></a>Consulte también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)
