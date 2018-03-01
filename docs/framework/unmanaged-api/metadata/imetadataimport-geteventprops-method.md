---
title: "IMetaDataImport::GetEventProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73f257c46fd21355eeaabbe9e1b5d2841d2c3911
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps (Método)
Obtiene información de metadatos para el evento representado por el símbolo (token) de evento especificado, incluidos el tipo declarativo, agregar y quitar métodos de delegados y todas las marcas y otros datos asociados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ev`  
 [in] El token de metadatos de evento que representa el evento para obtener metadatos.  
  
 `pClass`  
 [out] Un puntero al token de TypeDef que representa la clase que declara el evento.  
  
 `szEvent`  
 [out] El nombre del evento al que hace referencia `ev`.  
  
 `pchEvent`  
 [in] La longitud solicitada en caracteres anchos de `szEvent`.  
  
 `pdwEventFlags`  
 [out] La longitud devuelta en caracteres anchos de `szEvent`.  
  
 `ptkEventType`  
 [out] Un puntero a un TypeRef o TypeDef metadatos símbolo (token) que representa el <xref:System.Delegate> tipo de evento.  
  
 `pmdAddOn`  
 [out] Un puntero al token de metadatos que representa el método que agrega controladores para el evento.  
  
 `pmdRemoveOn`  
 [out] Un puntero al token de metadatos que representa el método que quita controladores para el evento.  
  
 `pmdFire`  
 [out] Un puntero al token de metadatos que representa el método que genera el evento.  
  
 `rmdOtherMethod`  
 [out] Una matriz de punteros token a otros métodos asociados al evento.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [out] El número de símbolos (tokens) devueltos en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
