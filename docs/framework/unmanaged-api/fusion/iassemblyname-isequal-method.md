---
title: IAssemblyName::IsEqual (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80402234d9374fa4f16e1f8bb315536a9bdfb2c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081520"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual (Método)
Determina si un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) es igual a este objeto `IAssemblyName`, en función de las marcas de comparación especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pName`  
 [in] El `IAssemblyName` objeto al que se compara este `IAssemblyName`.  
  
 `dwCmpFlags`  
 [in] Una combinación bit a bit de [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) valores que influyen en la comparación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (Interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Enumeraciones de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
