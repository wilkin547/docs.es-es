---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: 5434aa2d12bd9a29a8c2fc784421442469ceb1ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440554"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyRefProps (Método)
Modifica la estructura de metadatos `AssemblyRef` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ar`  
 de Símbolo (token) de metadatos que especifica el `AssemblyRef` estructura de metadatos que se va a modificar.  
  
 `pbPublicKeyOrToken`  
 de La clave pública del publicador del ensamblado al que se hace referencia.  
  
 `cbPublicKeyOrToken`  
 de Tamaño en bytes de `pbPublicKeyOrToken`.  
  
 `szName`  
 de Nombre del texto legible del ensamblado.  
  
 `pMetaData`  
 de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.  
  
 `pbHashValue`  
 de Puntero a los datos hash asociados al ensamblado.  
  
 `cbHashValue`  
 de Tamaño en bytes de `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 de Combinación bit a bit de valores de [AssemblyRefFlags (](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) que especifican los atributos del ensamblado al que se hace referencia.  
  
## <a name="remarks"></a>Comentarios  
 Para crear una estructura de metadatos de `AssemblyRef`, use el método [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
