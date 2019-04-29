---
title: AssemblyOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790109"
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
|optAssemOS|Cadena: codificada como: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Cadena: contiene la configuración regional del ensamblado.|  
|optAssemVersion|Cadena: codificada como: "Principal.secundaria.compilación.revisión".|  
|optAssemCompany|Cadena: contiene la empresa.|  
|optAssemProduct|Cadena: contiene el nombre del producto.|  
|optAssemProductVersion|Cadena (también conocido como InformationalVersion).|  
|optAssemCopyright|Cadena: contiene la información de copyright.|  
|optAssemTrademark|Cadena: contiene la información de marca comercial.|  
|optAssemKeyFile|String (nombre de archivo).|  
|optAssemKeyName|Cadena (el nombre de clave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|BOOL (también conocida como DelaySign).|  
|optAssemFileVersion|Cadena: codificada como "Major.Minor.Build.Revision" como ProductVersion.|  
|optAssemSatelliteVer|Cadena - codificada como "Principal.secundaria.compilación.revisión".|  
|optLastAssemOption|Un contador del número de elementos.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** alink.h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Vea también

- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
