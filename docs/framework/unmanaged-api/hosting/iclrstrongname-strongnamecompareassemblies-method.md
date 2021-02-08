---
description: 'Más información sobre: ICLRStrongName:: StrongNameCompareAssemblies ((método)'
title: ICLRStrongName::StrongNameCompareAssemblies (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: ab02312073f9caf5059ecf7b4eeddaef864bd7b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799659"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies (Método)

Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `wszAssembly1`  
 de Ruta de acceso al primer ensamblado.  
  
 `wszAssembly2`  
 de Ruta de acceso al segundo ensamblado.  
  
 `pdwResult`  
 enuncia Uno de los siguientes valores:  
  
- `SN_CMP_DIFFERENT` (0): especifica que los ensamblados contienen datos diferentes.  
  
- `SN_CMP_IDENTICAL` (1): especifica que los ensamblados son exactamente iguales, incluidas sus firmas y suma de comprobación.  
  
- `SN_CMP_SIGONLY` (2): especifica que los ensamblados solo se diferencian en la firma y la suma de comprobación.  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Observaciones  

 La firma de nombre seguro de un ensamblado consta del nombre de texto, la versión, la referencia cultural y el token de clave pública del ensamblado.  
  
## <a name="see-also"></a>Consulte también

- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
