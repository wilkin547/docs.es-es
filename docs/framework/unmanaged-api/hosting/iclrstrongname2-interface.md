---
description: 'Más información acerca de: interfaz Iclrstrongname2 ('
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
ms.openlocfilehash: 7442bd054af735e9f1b75b05feb8724dfa993f73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781797"
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2 (Interfaz)

Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx (Método)](strongnamegetpublickeyex-method.md)|Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.|  
|[StrongNameSignatureVerificationEx2 (Método)](strongnamesignatureverificationex2-method.md)|Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
