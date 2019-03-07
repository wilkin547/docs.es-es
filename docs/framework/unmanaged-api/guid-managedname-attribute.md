---
title: GUID_ManagedName (Atributo)
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ad6e4d1d03d8362123e65f16907880b18893f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496396"
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName (Atributo)
Define un atributo de interfaz personalizado que especifica el nombre de espacio de nombres administrado para una biblioteca de modelo (COM) del objeto de componente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>Parámetros  
 `value`  
 El nombre de espacio de nombres administrado para la biblioteca.  
  
## <a name="definition"></a>de esquema JSON  
 `GUID_ManagedName` se define en Cor.h como sigue:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Comentarios  
 Un atributo de interfaz personalizado define los metadatos de un objeto en la biblioteca de tipos.  
  
 Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> para recuperar el nombre administrado en el atributo.  
  
 Para obtener más información, consulte [atributos de interfaz](/cpp/windows/interface-attributes) documentación de referencia de Visual C++.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una definición de la biblioteca con el `GUID_ManagedName` atributo.  
  
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
 **Encabezado**: Cor.h
