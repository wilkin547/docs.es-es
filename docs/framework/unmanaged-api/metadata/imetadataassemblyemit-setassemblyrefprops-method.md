---
description: 'Más información acerca de: IMetaDataAssemblyEmit:: SetAssemblyRefProps ((método)'
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
ms.openlocfilehash: 704fff656b705bb246e2742ce991d41fcadcdfcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678177"
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
 de Token de metadatos que especifica la `AssemblyRef` estructura de metadatos que se va a modificar.  
  
 `pbPublicKeyOrToken`  
 de La clave pública del publicador del ensamblado al que se hace referencia.  
  
 `cbPublicKeyOrToken`  
 de Tamaño en bytes de `pbPublicKeyOrToken` .  
  
 `szName`  
 de Nombre del texto legible del ensamblado.  
  
 `pMetaData`  
 de Un puntero a una instancia de ASSEMBLYMETADATA (que contiene la versión, la plataforma y la información de configuración regional para el ensamblado.  
  
 `pbHashValue`  
 de Puntero a los datos hash asociados al ensamblado.  
  
 `cbHashValue`  
 de Tamaño en bytes de `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 de Combinación bit a bit de valores de [AssemblyRefFlags (](assemblyrefflags-enumeration.md) que especifican los atributos del ensamblado al que se hace referencia.  
  
## <a name="remarks"></a>Observaciones  

 Para crear una `AssemblyRef` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
