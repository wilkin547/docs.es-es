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
ms.openlocfilehash: 3736e7279056e015b157758b1233cf6dc5aa6d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720209"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps (Método)

Modifica la estructura de metadatos `Assembly` especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Token de metadatos que especifica la `Assembly` estructura de metadatos que se va a modificar.  
  
 `pbPublicKey`  
 de Puntero a la clave pública del publicador del ensamblado.  
  
 `cbPublicKey`  
 de Tamaño en bytes de `pbPublicKey` .  
  
 `ulHashAlgId`  
 de Identificador del algoritmo hash usado para aplicar un algoritmo hash a los archivos de ensamblado.  
  
 `szName`  
 de Nombre del texto legible del ensamblado.  
  
 `pMetaData`  
 de Puntero al ASSEMBLYMETADATA (que contiene información sobre la versión, la plataforma y la configuración regional para el ensamblado.  
  
 `dwAssemblyFlags`  
 de Combinación bit a bit de valores de [AssemblyFlags (](assemblyflags-enumeration.md) que especifican varios atributos del ensamblado.  
  
## <a name="remarks"></a>Comentarios  

 Para crear una `Assembly` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyEmit (Interfaz)](imetadataassemblyemit-interface.md)
