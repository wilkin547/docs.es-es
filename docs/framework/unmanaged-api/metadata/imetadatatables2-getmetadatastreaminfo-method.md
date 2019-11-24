---
title: IMetaDataTables2::GetMetaDataStreamInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 279e34689169d31ad89772e90155e7f50bdbac08
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426219"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>IMetaDataTables2::GetMetaDataStreamInfo (Método)
Gets the name, size, and contents of the metadata stream at the specified index.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ix`  
 [in] The index of the requested metadata stream.  
  
 `ppchName`  
 [out] A pointer to the name of the stream.  
  
 `ppv`  
 [out] A pointer to the metadata stream.  
  
 `pcb`  
 [out] The size, in bytes, of `ppv`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [IMetaDataTables (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
