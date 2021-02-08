---
description: 'Más información sobre: ICLRStrongName:: Strongnamesignatureverificationfromimage ((método)'
title: ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
ms.openlocfilehash: 5c1c3568dd0ad506c478525503f168d8b8c2dfbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781836"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a>ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)

Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbBase`  
 de Dirección virtual relativa del manifiesto del ensamblado asignado.  
  
 `dwLength`  
 de Tamaño, en bytes, de la imagen asignada.  
  
 `dwInFlags`  
 de Marcas que influyen en el comportamiento de la comprobación. Se admiten los valores siguientes:  
  
- `SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.  
  
- `SN_INFLAG_INSTALL` (0x00000002): especifica que esta es la primera comprobación realizada en esta imagen.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado será accesible únicamente para el usuario actual.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.  
  
- `SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.  
  
 `pdwOutFlags`  
 enuncia Marca para la información de salida adicional. Se admite el siguiente valor:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
