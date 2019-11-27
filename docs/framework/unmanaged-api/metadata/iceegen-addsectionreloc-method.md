---
title: ICeeGen::AddSectionReloc (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
ms.openlocfilehash: e5940f229e86b46bb8c5d5b2f9920a8261359f65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436410"
---
# <a name="iceegenaddsectionreloc-method"></a>ICeeGen::AddSectionReloc (Método)
Agrega una instrucción. reloc al código base.  
  
 Este método está obsoleto y no debe usarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `section`  
 de La sección de código en memoria a la que se va a agregar una instrucción. reloc.  
  
 `offset`  
 de Desplazamiento de la sección.  
  
 `relativeTo`  
 de Sección a la que hace referencia `offset`.  
  
 `relocType`  
 de Uno de los valores de [ceesectionreloctype (](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) , que indica el tipo de instrucción. reloc que se va a agregar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
