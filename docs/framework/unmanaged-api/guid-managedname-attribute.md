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
ms.openlocfilehash: 0127b6894f1095521f1b24fc8c0424dc7db824b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721054"
---
# <a name="guid_managedname-attribute"></a>GUID_ManagedName (Atributo)

Define un atributo de interfaz personalizada que especifica el nombre de espacio de nombres administrado para una biblioteca COM (modelo de objetos componentes).  
  
## <a name="syntax"></a>Sintaxis  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>Parámetros  

 `value`  
 Nombre del espacio de nombres administrado de la biblioteca.  
  
## <a name="definition"></a>Definición  

 `GUID_ManagedName` se define en Cor. h de la siguiente manera:  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Comentarios  

 Un atributo de interfaz personalizada define los metadatos de un objeto en la biblioteca de tipos.  
  
 Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> para recuperar el nombre administrado del atributo.  
  
 Para obtener más información, vea [atributos de interfaz](/cpp/windows/attributes/interface-attributes) en la documentación de referencia de Visual C++.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra una definición de biblioteca mediante el `GUID_ManagedName` atributo.  
  
```idl
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

 **Encabezado:** Cor. h
