---
title: SetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179389"
---
# <a name="setpekind-method"></a>SetPEKind (Método)
Determina el tipo ejecutable portátil, específico de la máquina o independiente de la máquina.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 ID del ensamblado.  
  
 `FileToken`  
 Token de archivo para el que se va a establecer el tipo PE. Puede ser `AssemblyID` NULL si no indica un netmodule sin enlazar.  
  
 `dwPEKind`  
 El tipo de PE, como se indica en [corPEKind (enumeración).](../metadata/corpekind-enumeration.md)  
  
 `dwMachine`  
 La arquitectura de la máquina de destino, como se indica en el encabezado NT.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se realiza correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Consulte también

- [GetPEKind (Método)](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [IALink (interfaz)](ialink-interface.md)
- [API de ALink](index.md)
