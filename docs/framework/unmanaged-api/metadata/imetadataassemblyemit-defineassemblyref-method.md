---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineAssemblyRef'
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
ms.openlocfilehash: e3c3acce77e6b0cb2943d66f3477898c90ea6251
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706713"
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
 de La clave pública del publicador del ensamblado al que se hace referencia. La función auxiliar [StrongNameTokenFromAssembly (](../strong-naming/strongnametokenfromassembly-function.md) se puede usar para obtener el hash de la clave pública que se va a pasar como este parámetro.  
  
 `cbPublicKeyOrToken`  
 de Tamaño en bytes de `pbPublicKeyOrToken` .  
  
 `szName`  
 de Nombre del texto legible del ensamblado. Este valor no debe superar los 1024 caracteres.  
  
 `pMetaData`  
 de Instancia de ASSEMBLYMETADATA (que contiene la información de la versión, la plataforma y la configuración regional del ensamblado al que se hace referencia.  
  
 `pbHashValue`  
 de Los datos hash asociados al ensamblado al que se hace referencia. Opcional.  
  
 `cbHashValue`  
 de Tamaño en bytes de `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 de Combinación bit a bit de los valores de [corassemblyflags (](corassemblyflags-enumeration.md) que influyen en el comportamiento del motor de ejecución.  
  
 `pmdar`  
 enuncia Puntero al `AssemblyRef` token de metadatos devuelto.  
  
## <a name="remarks"></a>Observaciones  

 `AssemblyRef`Se debe definir una estructura de metadatos para cada ensamblado al que haga referencia este ensamblado.  
  
 En tiempo de ejecución, los detalles de un ensamblado al que se hace referencia se pasan al solucionador del ensamblado con una indicación de que representan la información "como generada". A continuación, la resolución de ensamblado aplica la Directiva.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
