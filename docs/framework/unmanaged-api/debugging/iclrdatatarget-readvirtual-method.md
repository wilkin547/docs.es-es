---
title: ICLRDataTarget::ReadVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
ms.openlocfilehash: 83e2d1231b85086c2e65813cf427df3de36405b7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785310"
---
# <a name="iclrdatatargetreadvirtual-method"></a>ICLRDataTarget::ReadVirtual (Método)
Lee datos de la dirección de memoria virtual especificada en el búfer especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `address`  
 de CLRDATA_ADDRESS que almacena la dirección de memoria virtual.  
  
 `buffer`  
 enuncia Un puntero a un búfer que recibe los datos.  
  
 `bytesRequested`  
 de Longitud del búfer.  
  
 `bytesRead`  
 enuncia Puntero al número de bytes devueltos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)
