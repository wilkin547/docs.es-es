---
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
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177870"
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
 [en] Un token de `mdtFile` `mdtAssemblyRef` metadatos de tipo o que se asigna al proveedor de recursos. Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.  
  
 `dwOffset`  
 [en] Desplazamiento al principio del recurso dentro del archivo. Para los recursos en archivos independientes, esto siempre será cero. Si el recurso está incrustado en un archivo PE (ejecutable portátil), se trata de un desplazamiento del recurso BLOB, que comienza en la ubicación especificada en el archivo de encabezado cor.h.  
  
 `dwResourceFlags`  
 [en] Combinación bit a bit de valores de marca que especifican la configuración de propiedades para la definición de recursos.  
  
 `pmdmr`  
 [fuera] Un puntero al token de metadatos devuelto.  
  
## <a name="remarks"></a>Observaciones  
 Se `ManifestResource` debe definir una estructura de metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyEmit (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
