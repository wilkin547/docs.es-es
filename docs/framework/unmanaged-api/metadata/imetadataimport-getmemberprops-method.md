---
title: "IMetaDataImport::GetMemberProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 543929390977fc593e86947feece06f43bc0cad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps (Método)
Obtiene información de metadatos, incluidos el nombre, la firma binaria y la dirección virtual relativa, de la <xref:System.Type> miembro al que hace referencia el token de metadatos especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `mb`  
 [in] El token que hace referencia al miembro para obtener los metadatos asociados.  
  
 `pClass`  
 [out] Un puntero al token de metadatos que representa la clase del miembro.  
  
 `szMember`  
 [out] El nombre del miembro.  
  
 `cchMember`  
 [in] El tamaño en caracteres anchos de la `szMember` búfer.  
  
 `pchMember`  
 [out] El tamaño en caracteres anchos del nombre devuelto.  
  
 `pdwAttr`  
 [out] Los valores de marca que se aplica al miembro.  
  
 `ppvSigBlob`  
 [out] Un puntero a la firma de metadatos binaria del miembro.  
  
 `pcbSigBlob`  
 [out] El tamaño en bytes de `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Un puntero a la dirección virtual relativa del miembro.  
  
 `pdwImplFlags`  
 [out] Los marcadores de implementación de método asociados al miembro.  
  
 `pdwCPlusTypeFlag`  
 [out] Un indicador que marca un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Un valor de cadena constante devuelto por este miembro.  
  
 `pcchValue`  
 [out] El tamaño en caracteres de `ppValue`, o cero si `ppValue` no contiene una cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
