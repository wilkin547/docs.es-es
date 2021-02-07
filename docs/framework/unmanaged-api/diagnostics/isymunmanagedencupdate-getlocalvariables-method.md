---
description: 'Más información sobre: ISymUnmanagedENCUpdate:: Getlocalvariables ((método)'
title: ISymUnmanagedENCUpdate::GetLocalVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: bc034603dd6a09ea78dad789e11ea951d65e839b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721468"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>ISymUnmanagedENCUpdate::GetLocalVariables (Método)

Obtiene las variables locales.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mdMethodToken`  
 de Símbolo (token) de metadatos del método.  
  
 `cLocals`  
 de `ULONG` Que indica el tamaño del `rgLocals` parámetro.  
  
 `rgLocals`  
 enuncia Matriz de instancias de [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) devuelta.  
  
 `pceltFetched`  
 enuncia Un puntero a un `ULONG` que recibe el tamaño del `rgLocals` búfer necesario para contener las variables locales.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedENCUpdate (Interfaz)](isymunmanagedencupdate-interface.md)
