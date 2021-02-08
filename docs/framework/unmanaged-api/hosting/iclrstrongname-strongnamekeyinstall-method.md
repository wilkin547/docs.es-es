---
description: 'Más información sobre: ICLRStrongName:: StrongNameKeyInstall ((método)'
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
ms.openlocfilehash: 8f9e7bfebff555a6430a3970c8ee1c481e341f58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799517"
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
 de Tamaño, en bytes, de `pbKeyBlob` .  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="remarks"></a>Observaciones  

 Use el método [ICLRStrongName:: StrongNameKeyDelete (](iclrstrongname-strongnamekeydelete-method.md) para eliminar el contenedor de claves.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
