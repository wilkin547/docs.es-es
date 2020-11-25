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
ms.openlocfilehash: 14286970a4f7093d72b47b780ea880f5ccb1bca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721080"
---
# <a name="iinstallreferenceitemgetreference-method"></a>IInstallReferenceItem::GetReference (Método)

Obtiene un puntero a la estructura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) representada por este objeto [IInstallReferenceItem (](iinstallreferenceitem-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppRefData`  
 enuncia Puntero devuelto `FUSION_INSTALL_REFERENCE` .  
  
 `dwFlags`  
 [in] Reservado para extensibilidad futura. `dwFlags` debe ser 0 (cero).  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IInstallReferenceItem (Interfaz)](iinstallreferenceitem-interface.md)
- [FUSION_INSTALL_REFERENCE (Estructura)](fusion-install-reference-structure.md)
