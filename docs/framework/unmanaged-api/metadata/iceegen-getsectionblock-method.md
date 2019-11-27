---
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
ms.openlocfilehash: 0731053fb37c775d25052a5fd99a479a44ff5862
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434880"
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
  
## <a name="remarks"></a>Comentarios  
 Llame solo a `GetSectionBlock` si tiene requisitos de sección especiales que no se controlan mediante otros métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
