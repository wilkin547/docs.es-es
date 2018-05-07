---
title: IMetaDataImport::GetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95850448504fd863f2726a7fb7574436476a6dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps (Método)
Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `tk`  
 [in] Símbolo (token) de ParamDef que representa el parámetro para devolver los metadatos.  
  
 `pmd`  
 [out] Un puntero a un símbolo (token) de MethodDef que representa el método que toma el parámetro.  
  
 `pulSequence`  
 [out] La posición ordinal del parámetro en la lista de argumentos de método.  
  
 `szName`  
 [out] Un búfer para contener el nombre del parámetro.  
  
 `cchName`  
 [in] El tamaño solicitado en caracteres anchos de `szName`.  
  
 `pchName`  
 [out] El tamaño devuelto en caracteres anchos de `szName`.  
  
 `pdwAttr`  
 [out] Puntero a cualquier indicador de atributo asociado al parámetro.  
  
 `pdwCPlusTypeFlag`  
 [out] Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Un puntero a una cadena constante devuelta por el parámetro.  
  
 `pcchValue`  
 [out] El tamaño de `ppValue` en caracteres anchos, o cero si `ppValue` no contiene una cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
