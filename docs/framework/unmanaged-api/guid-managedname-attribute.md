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
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="c1bab-102">GUID_ManagedName (Atributo)</span><span class="sxs-lookup"><span data-stu-id="c1bab-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="c1bab-103">Define un atributo de interfaz personalizado que especifica el nombre de espacio de nombres administrado para una biblioteca de modelo (COM) del objeto de componente.</span><span class="sxs-lookup"><span data-stu-id="c1bab-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1bab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1bab-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1bab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1bab-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="c1bab-106">El nombre de espacio de nombres administrado para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c1bab-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="c1bab-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="c1bab-107">Definition</span></span>  
 <span data-ttu-id="c1bab-108">`GUID_ManagedName` se define en Cor.h como sigue:</span><span class="sxs-lookup"><span data-stu-id="c1bab-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c1bab-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1bab-109">Remarks</span></span>  
 <span data-ttu-id="c1bab-110">Un atributo de interfaz personalizado define los metadatos de un objeto en la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c1bab-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="c1bab-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> para recuperar el nombre administrado en el atributo.</span><span class="sxs-lookup"><span data-stu-id="c1bab-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="c1bab-112">Para obtener más información, consulte [atributos de interfaz](/cpp/windows/interface-attributes) documentación de referencia de Visual C++.</span><span class="sxs-lookup"><span data-stu-id="c1bab-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1bab-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1bab-113">Example</span></span>  
 <span data-ttu-id="c1bab-114">El ejemplo siguiente muestra una definición de la biblioteca con el `GUID_ManagedName` atributo.</span><span class="sxs-lookup"><span data-stu-id="c1bab-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="c1bab-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1bab-115">Requirements</span></span>  
 <span data-ttu-id="c1bab-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1bab-116">**Header:** Cor.h</span></span>
