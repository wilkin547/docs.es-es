---
description: 'Más información sobre: ICeeGen:: AddSectionReloc ((método)'
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
ms.openlocfilehash: 715c506f0bdcb3fcef33b3e9165d1f9ae47c6073
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707181"
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
 de La sección a la que `offset` hace referencia.  
  
 `relocType`  
 de Uno de los valores de [ceesectionreloctype (](ceesectionreloctype-enumeration.md) , que indica el tipo de instrucción. reloc que se va a agregar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICeeGen (Interfaz)](iceegen-interface.md)
