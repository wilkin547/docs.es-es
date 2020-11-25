---
title: IMetaDataAssemblyEmit::SetFileProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 9cf5f3d926c1e742dd9134e7bf292df53e1a4909
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720183"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>IMetaDataAssemblyEmit::SetFileProps (Método)

Modifica la estructura de metadatos `File` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `file`  
 de Token de metadatos que especifica la `File` estructura de metadatos que se va a modificar.  
  
 `pbHashValue`  
 de Puntero a los datos hash asociados al archivo.  
  
 `cbHashValue`  
 de Tamaño en bytes de `pbHashValue` .  
  
 `dwFileFlags`  
 de Combinación bit a bit de valores de [CorFileFlags (](corfileflags-enumeration.md) que especifican varios atributos del archivo.  
  
## <a name="remarks"></a>Comentarios  

 Para crear una `File` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
