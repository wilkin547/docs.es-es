---
description: 'Más información acerca de: GUID_ManagedName atributo'
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
ms.openlocfilehash: c139e8bdc00aa3b008a706de0c42cfbf8e3510c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799998"
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
  
## <a name="remarks"></a>Observaciones  

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
