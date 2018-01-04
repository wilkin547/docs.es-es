---
title: GUID_ManagedName (Atributo)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GUID_ManagedName
api_location: alink.dll
api_type: COM
f1_keywords: GUID_ManagedName
helpviewer_keywords: GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 116a9e38b9885f0d0a5afc8f4915b9ce2b50f1dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName (Atributo)
Define un atributo de interfaz personalizado que especifica el nombre de espacio de nombres administrado para una biblioteca de (componentes COM) del modelo de objetos de componente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a>Parámetros  
 `value`  
 El nombre de espacio de nombres administrado para la biblioteca.  
  
## <a name="definition"></a>Definición  
 `GUID_ManagedName`se define en Cor.h como sigue:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Comentarios  
 Un atributo de interfaz personalizado define los metadatos de un objeto en la biblioteca de tipos.  
  
 Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> para recuperar el nombre administrado del atributo.  
  
 Para obtener más información, consulte [atributos de la interfaz](/cpp/windows/interface-attributes) documentación de referencia de Visual C++.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una definición de biblioteca mediante el `GUID_ManagedName` atributo.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** Cor.h
