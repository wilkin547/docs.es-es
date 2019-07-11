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
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742268"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions (Enumeración)
Enumera las opciones de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="fields"></a>Fields  
  
|Campo|DESCRIPCIÓN|  
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
