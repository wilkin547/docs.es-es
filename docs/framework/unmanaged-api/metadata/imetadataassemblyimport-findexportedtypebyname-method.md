---
title: IMetaDataAssemblyImport::FindExportedTypeByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731597"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>IMetaDataAssemblyImport::FindExportedTypeByName (Método)

Obtiene un puntero a un tipo exportado, dado su nombre y tipo envolvente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szName`  
 de Nombre del tipo exportado.  
  
 `mdtExportedType`  
 de Símbolo (token) de metadatos para la clase envolvente del tipo exportado. Este valor es `mdExportedTypeNil` si el tipo exportado solicitado no es un tipo anidado.  
  
 `ptkExportedType`  
 enuncia Puntero al `mdExportedType` token que representa el tipo exportado.  
  
## <a name="remarks"></a>Comentarios  

 El `FindExportedTypeByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataAssemblyImport (Interfaz)](imetadataassemblyimport-interface.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../deployment/how-the-runtime-locates-assemblies.md)
