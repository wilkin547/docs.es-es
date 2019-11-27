---
title: IMetaDataAssemblyEmit::DefineAssembly (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 20628e708261076c6e172ff30c366a0d69c2e0f2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432124"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly (Método)
Crea una estructura de `Assembly` que contiene metadatos para el ensamblado especificado y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbPublicKey`  
 de La clave pública que identifica al publicador del ensamblado, o NULL si el ensamblado no tiene un nombre seguro.  
  
 `cbPublicKey`  
 de Tamaño en bytes de `pbPublicKey`.  
  
 `uHashAlgId`  
 de Identificador del algoritmo hash que se va a utilizar para cifrar los archivos del ensamblado, o NULL para especificar el algoritmo SHA-1.  
  
 `szName`  
 de Nombre del texto legible del ensamblado. Este valor no debe superar los 1024 caracteres.  
  
 `pMetaData`  
 de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.  
  
 `dwAssemblyFlags`  
 de Combinación de valores [corassemblyflags (](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) que describen las características del ensamblado.  
  
 `pmda`  
 enuncia Puntero al token de metadatos.  
  
## <a name="remarks"></a>Comentarios  
 Solo se puede definir una estructura de metadatos de `Assembly` dentro de un manifiesto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
