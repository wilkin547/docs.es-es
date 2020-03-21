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
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176089"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock (Método)
Obtiene un bloque de sección de la base de código.  
  
 Este método está obsoleto y no se debe utilizar.  
  
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
 [en] La sección desde la que se va a recuperar un bloque de la base de código.  
  
 `len`  
 [en] La longitud del bloque que se va a recuperar.  
  
 `align`  
 [en] El byte, relativo al principio de la sección, con el que alinear el primer byte del bloque. Esta es la posición del bloque dentro de la sección.  
  
 `ppBytes`  
 [fuera] Puntero a una ubicación que recibe la dirección del bloque recuperado.  
  
## <a name="remarks"></a>Observaciones  
 Llame `GetSectionBlock` solamente si usted tiene los requisitos de la sección especial que no son manejados por otros métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICeeGen (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
