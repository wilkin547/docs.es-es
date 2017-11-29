---
title: "AssemblyOptions (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions (Enumeración)
Enumera las opciones de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Campos  
  
|Campo|Descripción|  
|-----------|-----------------|  
|optAssemTitle|Cadena: representa el título del ensamblado.|  
|optAssemDescription|Cadena: contiene la descripción del ensamblado.|  
|optAssemConfig|Cadena: contiene la configuración del ensamblado.|  
|optAssemOS|Cadena: está codificada como: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Cadena: contiene la configuración regional del ensamblado.|  
|optAssemVersion|Cadena: está codificada como: "Principal.secundaria.compilación.revisión".|  
|optAssemCompany|Cadena: contiene la empresa.|  
|optAssemProduct|Cadena: contiene el nombre del producto.|  
|optAssemProductVersion|Cadena (también conocido como InformationalVersion).|  
|optAssemCopyright|Cadena: contiene la información de copyright.|  
|optAssemTrademark|Cadena: contiene la información de marca comercial.|  
|optAssemKeyFile|Cadena (nombre de archivo).|  
|optAssemKeyName|Cadena (el nombre de clave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|BOOL (también conocido como DelaySign).|  
|optAssemFileVersion|Cadena: está codificada como "Major.Minor.Build.Revision" como ProductVersion.|  
|optAssemSatelliteVer|Cadena: está codificada como "Major.Minor.Build.Revision".|  
|optLastAssemOption|Un contador del número de elementos.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** alink.h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Vea también  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
