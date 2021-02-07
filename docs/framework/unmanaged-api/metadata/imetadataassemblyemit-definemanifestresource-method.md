---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineManifestResource'
title: IMetaDataAssemblyEmit::DefineManifestResource (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 53994f1777cbd2e019f14c0ccae375e6424de509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678333"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource (Método)

Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szName`  
 [in] Nombre del recurso.  
  
 `tkImplementation`  
 de Símbolo (token) de metadatos de tipo `mdtFile` o `mdtAssemblyRef` que se asigna al proveedor de recursos. Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.  
  
 `dwOffset`  
 de Desplazamiento al principio del recurso dentro del archivo. En el caso de los recursos de archivos independientes, siempre será cero. Si el recurso está incrustado en un archivo PE (portable ejecutable), se trata de un desplazamiento del BLOB de recursos, que se inicia en la ubicación especificada en el archivo de encabezado Cor. h.  
  
 `dwResourceFlags`  
 de Combinación bit a bit de valores de marca que especifican los valores de propiedad para la definición de recursos.  
  
 `pmdmr`  
 enuncia Puntero al token de metadatos devuelto.  
  
## <a name="remarks"></a>Observaciones  

 `ManifestResource`Se debe definir una estructura de metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
