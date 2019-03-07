---
title: IMetaDataImport::GetEventProps (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f2eec9fce1909f6a83190f5ba3e99162461bbc4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492158"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps (Método)
Obtiene información de metadatos para el evento representado por el token de evento especificado, incluidos el tipo declarativo, agregar y quitar métodos para los delegados y los indicadores y otros datos asociados.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `ev`  
 [in] El token de metadatos de evento que representa el evento para obtener metadatos.  
  
 `pClass`  
 [out] Un puntero al token de TypeDef que representa la clase que declara el evento.  
  
 `szEvent`  
 [out] El nombre del evento al que hace referencia `ev`.  
  
 `pchEvent`  
 [in] La longitud en caracteres anchos de solicitado `szEvent`.  
  
 `pdwEventFlags`  
 [out] La longitud devuelta en caracteres anchos de `szEvent`.  
  
 `ptkEventType`  
 [out] Un puntero a un token TypeRef o TypeDef metadatos token que representa el <xref:System.Delegate> tipo del evento.  
  
 `pmdAddOn`  
 [out] Un puntero al token de metadatos que representa el método que agrega controladores para el evento.  
  
 `pmdRemoveOn`  
 [out] Un puntero al token de metadatos que representa el método que quita controladores para el evento.  
  
 `pmdFire`  
 [out] Un puntero al token de metadatos que representa el método que genera el evento.  
  
 `rmdOtherMethod`  
 [out] Una matriz de punteros de token a otros métodos asociados al evento.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [out] El número de tokens que se devuelven en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
