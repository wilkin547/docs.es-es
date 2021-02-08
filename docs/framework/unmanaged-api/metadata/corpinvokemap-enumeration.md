---
description: 'Más información sobre: enumeración CorPinvokeMap ('
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
ms.openlocfilehash: 8285632725096b4e6afc85fe54a89f12fc899dd1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784267"
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap (Enumeración)

Especifica las opciones de una llamada PInvoke.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pmNoMangle`|Use cada nombre de miembro como se especifica.|  
|`pmCharSetMask`|Reservado.|  
|`pmCharSetNotSpec`|Reservado.|  
|`pmCharSetAnsi`|Calcula las referencias de las cadenas como cadenas de caracteres de varios bytes.|  
|`pmCharSetUnicode`|Calcula referencias de las cadenas como caracteres Unicode de 2 bytes.|  
|`pmCharSetAuto`|Calcula automáticamente las referencias de las cadenas como corresponde al sistema operativo de destino. El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003. el valor predeterminado es ANSI en Windows 98 y Windows me.|  
|`pmBestFitUseAssem`|Reservado.|  
|`pmBestFitEnabled`|Realice la asignación con ajuste perfecto de caracteres Unicode que no tienen una coincidencia exacta en el juego de caracteres ANSI.|  
|`pmBestFitDisabled`|No realice la asignación con ajuste perfecto de caracteres Unicode. En este caso, todos los caracteres no asignables se reemplazarán por un carácter "?".|  
|`pmBestFitMask`|Reservado.|  
|`pmThrowOnUnmappableCharUseAssem`|Reservado.|  
|`pmThrowOnUnmappableCharEnabled`|Produce una excepción cuando el serializador de interoperabilidad encuentra un carácter que no se pudo asignar.|  
|`pmThrowOnUnmappableCharDisabled`|No inicie una excepción cuando el serializador de interoperabilidad encuentre un carácter no asignable.|  
|`pmThrowOnUnmappableCharMask`|Reservado|  
|`pmSupportsLastError`|Permita que el destinatario llame a la `SetLastError` función de Win32 antes de volver del método con atributos.|  
|`pmCallConvMask`|Reservado|  
|`pmCallConvWinapi`|Usar la Convención de llamada de plataforma predeterminada. Por ejemplo, en Windows el valor predeterminado es `StdCall` y en Windows CE .net es `Cdecl` .|  
|`pmCallConvCdecl`|Utilice la `Cdecl` Convención de llamada. En este caso, el autor de la llamada limpia la pila. Esto permite llamar a funciones con `varargs` (es decir, funciones que aceptan un número variable de parámetros).|  
|`pmCallConvStdcall`|Utilice la `StdCall` Convención de llamada. En este caso, el destinatario limpia la pila. Esta es la convención predeterminada para la llamada a funciones no administradas con invocación de plataforma.|  
|`pmCallConvThiscall`|Utilice la `ThisCall` Convención de llamada. En este caso, el primer parámetro es el `this` puntero y se almacena en la ECx de registro. Los demás parámetros se insertan en la pila. La `ThisCall` Convención de llamada se usa para llamar a métodos en clases exportadas desde un archivo dll no administrado.|  
|`pmCallConvFastcall`|Reservado.|  
|`pmMaxValue`|Reservado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
