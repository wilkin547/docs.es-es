---
description: 'Más información sobre: IMetaDataImport:: Getnativecallconvfromsig ((método)'
title: IMetaDataImport::GetNativeCallConvFromSig (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
ms.openlocfilehash: 2fb5c347098f860f9ad32eab20c8b5bd6278f838
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677579"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a>IMetaDataImport::GetNativeCallConvFromSig (Método)

Obtiene la convención de llamada nativa del método representado por el puntero de firma especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pvSig`  
 de Puntero a la firma de metadatos del método para el que se va a devolver la Convención de llamada.  
  
 `cbSig`  
 de Tamaño en bytes de `pvSig` .  
  
 `pCallConv`  
 enuncia Puntero a la Convención de llamada nativa.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.CallingConvention>
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
