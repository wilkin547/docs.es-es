---
title: IAssemblyName::GetDisplayName (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
ms.openlocfilehash: 5dbb5dc483bc5a08c59606654d55b5a62266e509
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134368"
---
# <a name="iassemblynamegetdisplayname-method"></a>IAssemblyName::GetDisplayName (Método)
Obtiene el nombre legible del ensamblado al que hace referencia este objeto [IAssemblyName](iassemblyname-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szDisplayName`  
 enuncia Búfer de cadena que contiene el nombre del ensamblado al que se hace referencia.  
  
 `pccDisplayName`  
 [in, out] Tamaño de `szDisplayName` en caracteres anchos, incluido un carácter de terminador nulo.  
  
 `dwDisplayFlags`  
 de Combinación bit a bit de los valores de [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) que influyen en las características de `szDisplayName`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (interfaz)](iassemblyname-interface.md)
- [Enumeraciones de fusión](fusion-enumerations.md)
