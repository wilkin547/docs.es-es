---
title: ICLRStrongName::StrongNameKeyInstall (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
ms.openlocfilehash: 693a5831934647256ac48c8f3a2d30325dee4349
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135040"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a>ICLRStrongName::StrongNameKeyInstall (Método)
Importa un par de claves pública y privada a un contenedor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszKeyContainer`  
 de Nombre del contenedor de claves. `wszKeyContainer` debe ser una cadena no vacía.  
  
 `pbKeyBlob`  
 de Par de claves binarias.  
  
 `cbKeyBlob`  
 de Tamaño, en bytes, de `pbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).  
  
## <a name="remarks"></a>Comentarios  
 Use el método [ICLRStrongName:: StrongNameKeyDelete (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) para eliminar el contenedor de claves.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameKeyDelete (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
