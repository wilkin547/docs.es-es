---
title: IMetaDataAssemblyImport::GetAssemblyFromScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: 953aa16566c2a15939fbd556f478bbdb3c0c77d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448243"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a>IMetaDataAssemblyImport::GetAssemblyFromScope (Método)
Obtiene un puntero al ensamblado en el ámbito actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ptkAssembly`  
 enuncia Puntero al token de `mdAssembly` recuperado que identifica el ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
