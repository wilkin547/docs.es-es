---
description: 'Más información sobre: ICLRStrongName:: Strongnamegetblobfromimage ((método)'
title: ICLRStrongName::StrongNameGetBlobFromImage (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: 32f04e21f1f08f3872ccdd27a64f39ea29d7e060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799621"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a>ICLRStrongName::StrongNameGetBlobFromImage (Método)

Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbBase`  
 de Dirección de memoria del manifiesto del ensamblado asignado.  
  
 `dwLength`  
 de Tamaño, en bytes, de la imagen en `pbBase` .  
  
 `pbBlob`  
 de Búfer que va a contener la representación binaria de la imagen.  
  
 `pcbBlob`  
 [in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` . Después de la devolución, el tamaño real, en bytes, de `pbBlob` .  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameGetBlob](iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
