---
title: ICeeGen::GetSectionCreate (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 2c3c3a0168216902e5982b7d0193e72acc2bdf47
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448099"
---
# <a name="iceegengetsectioncreate-method"></a>ICeeGen::GetSectionCreate (Método)
Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.  
  
 Este método está obsoleto y no debe usarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 de Puntero a una cadena que especifica el nombre de la sección que se va a crear.  
  
 `flags`  
 de Marcas que especifican las opciones.  
  
 `section`  
 enuncia Un puntero a la sección de código que se acaba de crear.  
  
## <a name="remarks"></a>Comentarios  
 Llame solo a `GetSectionCreate` si tiene requisitos de sección especiales que no se controlan mediante otros métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
