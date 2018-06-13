---
title: CorPinvokeMap (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: edb45c9ceefb242e5a72e8602dc93ecd39b2df09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447959"
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap (Enumeración)
Especifica opciones para una llamada PInvoke.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pmNoMangle`|Utilice el nombre de cada miembro tal como se especifica.|  
|`pmCharSetMask`|Reservado.|  
|`pmCharSetNotSpec`|Reservado.|  
|`pmCharSetAnsi`|Calcular las referencias de cadenas como cadenas de caracteres de varios bytes.|  
|`pmCharSetUnicode`|Calcular las referencias de cadenas como caracteres de 2 bytes de Unicode.|  
|`pmCharSetAuto`|Calcula automáticamente las referencias de cadenas de forma adecuada para el sistema operativo de destino. El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003; el valor predeterminado es ANSI en Windows 98 y Windows Millennium Edition.|  
|`pmBestFitUseAssem`|Reservado.|  
|`pmBestFitEnabled`|Realizar una asignación con ajuste perfecto de caracteres Unicode que no tienen a una coincidencia exacta en el juego de caracteres ANSI.|  
|`pmBestFitDisabled`|No realice la asignación con ajuste perfecto de caracteres Unicode. En este caso, todos los caracteres no asignables se reemplazará por un '?'.|  
|`pmBestFitMask`|Reservado.|  
|`pmThrowOnUnmappableCharUseAssem`|Reservado.|  
|`pmThrowOnUnmappableCharEnabled`|Inicia una excepción cuando el serializador de interoperabilidad encuentra un carácter no asignable.|  
|`pmThrowOnUnmappableCharDisabled`|No producen una excepción cuando el serializador de interoperabilidad encuentra un carácter no asignable.|  
|`pmThrowOnUnmappableCharMask`|Reservada|  
|`pmSupportsLastError`|Permitir al destinatario llamar a Win32 `SetLastError` función antes de volver del método con atributos.|  
|`pmCallConvMask`|Reservada|  
|`pmCallConvWinapi`|Use la convención de llamada de plataforma predeterminada. Por ejemplo, en Windows, el valor predeterminado es `StdCall` y en Windows CE .NET es `Cdecl`.|  
|`pmCallConvCdecl`|Use la `Cdecl` convención de llamada. En este caso, el llamador limpia la pila. Esto permite llamar a funciones con `varargs` (es decir, las funciones que aceptan un número variable de parámetros).|  
|`pmCallConvStdcall`|Use la `StdCall` convención de llamada. En este caso, el destinatario limpia la pila. Esta es la convención predeterminada para llamar a funciones no administradas con la plataforma de invocación.|  
|`pmCallConvThiscall`|Use la `ThisCall` convención de llamada. En este caso, el primer parámetro es el `this` puntero y se almacena en el registro ECX. Otros parámetros se insertan en la pila. El `ThisCall` convención de llamada se usa para llamar a métodos en clases exportadas desde una DLL no administrada.|  
|`pmCallConvFastcall`|Reservado.|  
|`pmMaxValue`|Reservado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
