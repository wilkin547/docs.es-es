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
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432080"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef (Método)
Crea una estructura `AssemblyRef` que contiene los metadatos para el ensamblado al que este ensamblado hace referencia y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de La clave pública del publicador del ensamblado al que se hace referencia. La función auxiliar [StrongNameTokenFromAssembly (](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) se puede usar para obtener el hash de la clave pública que se va a pasar como este parámetro.  
  
 `cbPublicKeyOrToken`  
 de Tamaño en bytes de `pbPublicKeyOrToken`.  
  
 `szName`  
 de Nombre del texto legible del ensamblado. Este valor no debe superar los 1024 caracteres.  
  
 `pMetaData`  
 de Instancia de ASSEMBLYMETADATA (que contiene la información de la versión, la plataforma y la configuración regional del ensamblado al que se hace referencia.  
  
 `pbHashValue`  
 de Los datos hash asociados al ensamblado al que se hace referencia. Opcional.  
  
 `cbHashValue`  
 de Tamaño en bytes de `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 de Combinación bit a bit de los valores de [corassemblyflags (](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) que influyen en el comportamiento del motor de ejecución.  
  
 `pmdar`  
 enuncia Puntero al token de metadatos de `AssemblyRef` devuelto.  
  
## <a name="remarks"></a>Comentarios  
 Se debe definir una `AssemblyRef` estructura de metadatos para cada ensamblado al que hace referencia este ensamblado.  
  
 En tiempo de ejecución, los detalles de un ensamblado al que se hace referencia se pasan al solucionador del ensamblado con una indicación de que representan la información "como generada". A continuación, la resolución de ensamblado aplica la Directiva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
