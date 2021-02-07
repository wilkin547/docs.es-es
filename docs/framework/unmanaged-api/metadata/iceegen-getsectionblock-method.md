---
description: 'Más información sobre: ICeeGen:: Getsectionblock ((método)'
title: ICeeGen::GetSectionBlock (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: d1a9fdeb35507f9dd6528b581be877049d2a1478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721156"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock (Método)

Obtiene un bloque de sección del código base.  
  
 Este método está obsoleto y no debe usarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>Parámetros  

 `section`  
 de La sección de la que se va a recuperar un bloque del código base.  
  
 `len`  
 de Longitud del bloque que se va a recuperar.  
  
 `align`  
 de Byte, con respecto al principio de la sección, con el que se va a alinear el primer byte del bloque. Esta es la posición del bloque dentro de la sección.  
  
 `ppBytes`  
 enuncia Puntero a una ubicación que recibe la dirección del bloque recuperado.  
  
## <a name="remarks"></a>Observaciones  

 Llame `GetSectionBlock` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICeeGen (Interfaz)](iceegen-interface.md)
