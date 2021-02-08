---
description: 'Más información sobre: IMetaDataImport:: findMethod ((método)'
title: IMetaDataImport::FindMethod (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 0d2866554fcb4dcf3984310e4da24d501f1fc7b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803560"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod (Método)

Obtiene un puntero al token MethodDef para el método que está incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `td`  
 de El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se va a buscar. Si este valor es `mdTokenNil` , la búsqueda se realiza para una función global.  
  
 `szName`  
 de Nombre del método que se va a buscar.  
  
 `pvSigBlob`  
 de Puntero a la firma de metadatos binarios del método.  
  
 `cbSigBlob`  
 de Tamaño en bytes de `pvSigBlob` .  
  
 `pmb`  
 enuncia Puntero al token MethodDef coincidente.  
  
## <a name="remarks"></a>Observaciones  

 El método se especifica mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ). Puede haber varios métodos con el mismo nombre en una clase o interfaz. En ese caso, pase la Signatura del método para buscar la coincidencia única.  
  
 La firma que se pasa a `FindMethod` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado. Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor. El token es un índice en la tabla TypeDef local. No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la entrada a `FindMethod` .  
  
 `FindMethod` busca solo los métodos que se definieron directamente en la clase o la interfaz; no se encuentran los métodos heredados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
