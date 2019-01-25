---
title: IMetaDataConverter::GetTypeLibFromMetaData (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a6c39989a37f46d684c3a467d5e099ea7167185
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624137"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a>IMetaDataConverter::GetTypeLibFromMetaData (Método)
Obtiene un puntero a un `ITypeLib` instancia que representa la biblioteca de tipos con los nombres de biblioteca y el módulo especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `strModule`  
 [in] El nombre del módulo de la biblioteca de tipos.  
  
 `strTlbName`  
 [in] El nombre de la biblioteca de tipos.  
  
 `ppITL`  
 [out] Un puntero a una ubicación que recibe la dirección de la `ITypeLib` instancia que representa la biblioteca de tipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataConverter (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
