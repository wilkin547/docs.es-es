---
title: COINITIEE (Enumeración)
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005913"
---
# <a name="coinitiee-enumeration"></a>COINITIEE (Enumeración)
Especifica las constantes utilizadas por el [Coinicializador](../hosting/coinitializeee-function.md) al inicializar el Common Language Runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Modo de inicialización predeterminado. Esto inicializa el tiempo de ejecución y crea el valor predeterminado <xref:System.AppDomain> .|  
|`COINITEE_DLL`|Inicializa para ejecutar un archivo DLL administrado.|  
|`COINITEE_MAIN`|Inicializa para ejecutar un ejecutable administrado. Esto inicializa el tiempo de ejecución, pero no crea el valor predeterminado <xref:System.AppDomain> , que se crea después de escribir la rutina principal del archivo exe.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
