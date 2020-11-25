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
ms.openlocfilehash: 0fabf8159c2626d4e1716e3be60baaf1ec834032
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712994"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual (Método)

Determina si un objeto de [IAssemblyName](iassemblyname-interface.md) especificado es igual a este `IAssemblyName` , en función de las marcas de comparación especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pName`  
 de Objeto con el que se va a `IAssemblyName` comparar `IAssemblyName` .  
  
 `dwCmpFlags`  
 de Combinación bit a bit de valores de [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) que influyen en la comparación.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IAssemblyName (Interfaz)](iassemblyname-interface.md)
- [Enumeraciones de fusión](fusion-enumerations.md)
