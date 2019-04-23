---
title: IMetaDataAssemblyEmit::DefineAssemblyRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e480c408c10eb9e135f260426750f7747e5d8ce5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117357"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef (Método)
Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbPublicKeyOrToken`  
 [in] La clave pública del publicador del ensamblado que se hace referencia. La función auxiliar [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) puede usarse para obtener el hash de la clave pública para pasar como este parámetro.  
  
 `cbPublicKeyOrToken`  
 [in] El tamaño en bytes de `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] El nombre de texto legible del ensamblado. Este valor no debe superar los 1024 caracteres.  
  
 `pMetaData`  
 [in] Una instancia ASSEMBLYMETADATA que contiene la información de versión, la plataforma y la configuración regional del ensamblado que se hace referencia.  
  
 `pbHashValue`  
 [in] El hash de datos asociados al ensamblado que se hace referencia. Opcional.  
  
 `cbHashValue`  
 [in] El tamaño en bytes de `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Una combinación bit a bit de [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores que influyen en el comportamiento del motor de ejecución.  
  
 `pmdar`  
 [out] Un puntero a la devuelta `AssemblyRef` token de metadatos.  
  
## <a name="remarks"></a>Comentarios  
 Una `AssemblyRef` estructura de los metadatos debe definirse para cada ensamblado al que hace referencia este ensamblado.  
  
 En tiempo de ejecución, los detalles de un ensamblado de referencia se pasan a la resolución de ensamblado con un valor que indica que representan el "información"compilada. La resolución de ensamblado, a continuación, aplica la directiva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
