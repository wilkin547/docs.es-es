---
title: IMetaDataAssemblyEmit::SetAssemblyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3361212f9a7f7ff0739e8544419a2b67abc8f457
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214655"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps (Método)
Modifica la estructura de metadatos `Assembly` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pma`  
 [in] El token de metadatos que especifica el `Assembly` estructura de metadatos que se puede modificar.  
  
 `pbPublicKey`  
 [in] Un puntero a la clave pública del publicador del ensamblado.  
  
 `cbPublicKey`  
 [in] El tamaño en bytes de `pbPublicKey`.  
  
 `ulHashAlgId`  
 [in] El identificador del algoritmo hash que usa un algoritmo hash a los archivos de ensamblado a.  
  
 `szName`  
 [in] El nombre de texto legible del ensamblado.  
  
 `pMetaData`  
 [in] Un puntero a la ASSEMBLYMETADATA que contiene información de versión, la plataforma y la configuración regional para el ensamblado.  
  
 `dwAssemblyFlags`  
 [in] Una combinación bit a bit de [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) valores que especifican distintos atributos del ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 Para crear un `Assembly` estructura de los metadatos, use el [DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
