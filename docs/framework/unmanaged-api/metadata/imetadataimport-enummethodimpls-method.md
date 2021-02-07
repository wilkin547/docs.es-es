---
description: 'Más información sobre: IMetaDataImport:: Enummethodimpls ((método)'
title: IMetaDataImport::EnumMethodImpls (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: 3ae5795bdde36ad07c447370553e24e1ceacf493
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670702"
---
# <a name="imetadataimportenummethodimpls-method"></a>IMetaDataImport::EnumMethodImpls (Método)

Enumera los tokens MethodBody y MethodDeclaration que representan métodos del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `phEnum`  
 [in, out] Puntero al enumerador. Debe ser NULL para la primera llamada de este método.  
  
 `td`  
 de Un token de TypeDef para el tipo cuyas implementaciones de método se van a enumerar.  
  
 `rMethodBody`  
 enuncia Matriz en la que se van a almacenar los tokens de MethodBody.  
  
 `rMethodDecl`  
 enuncia Matriz en la que se van a almacenar los tokens MethodDeclaration.  
  
 `cMax`  
 de Tamaño máximo de las `rMethodBody` matrices y `rMethodDecl` .  
  
 `pcTokens`  
 de Número real de métodos devueltos en `rMethodBody` y `rMethodDecl` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodImpls` se devolvió correctamente.|  
|`S_FALSE`|No hay tokens de método para enumerar. En ese caso, `pcTokens` es cero.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
