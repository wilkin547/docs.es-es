---
title: ICLRStrongName2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092243"
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2 (Interfaz)
Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx (método)](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.|  
|[StrongNameSignatureVerificationEx2 (método)](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
