---
title: IInstallReferenceItem::GetReference (Método)
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213368"
---
# <a name="iinstallreferenceitemgetreference-method"></a>IInstallReferenceItem::GetReference (Método)
Obtiene un puntero a la [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) estructura representada por este [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppRefData`  
 [out] El valor devuelto `FUSION_INSTALL_REFERENCE` puntero.  
  
 `dwFlags`  
 [in] Reservado para extensibilidad futura. `dwFlags` debe ser 0 (cero).  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IInstallReferenceItem (Interfaz)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [FUSION_INSTALL_REFERENCE (Estructura)](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
