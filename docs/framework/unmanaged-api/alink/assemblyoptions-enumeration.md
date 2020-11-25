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
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717036"
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
  
## <a name="fields"></a>Campos  
  
|Campo|Descripción|  
|-----------|-----------------|  
|optAssemTitle|Cadena: representa el título del ensamblado.|  
|optAssemDescription|Cadena: contiene la descripción del ensamblado.|  
|optAssemConfig|Cadena: contiene la configuración del ensamblado.|  
|optAssemOS|Codificada por cadena como: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Cadena: contiene la configuración regional del ensamblado.|  
|optAssemVersion|Codificado por cadena como: "Major. minor. Build. revision".|  
|optAssemCompany|Cadena: contiene la compañía.|  
|optAssemProduct|Cadena: contiene el nombre del producto.|  
|optAssemProductVersion|Cadena (también conocida como InformationalVersion).|  
|optAssemCopyright|Cadena: contiene la información de copyright.|  
|optAssemTrademark|Cadena: contiene la información de marca comercial.|  
|optAssemKeyFile|Cadena (nombre de archivo).|  
|optAssemKeyName|Cadena (el nombre de la clave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (también conocido como DelaySign).|  
|optAssemFileVersion|Codificación de cadena como "Major. minor. Build. revision", igual que ProductVersion.|  
|optAssemSatelliteVer|Codificación de cadena como "Major. minor. Build. revision".|  
|optLastAssemOption|Contador del número de elementos.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ALink. h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Consulte también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
