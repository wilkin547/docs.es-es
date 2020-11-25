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
# <a name="guid_managedname-attribute"></a><span data-ttu-id="39949-102">GUID_ManagedName (Atributo)</span><span class="sxs-lookup"><span data-stu-id="39949-102">GUID_ManagedName Attribute</span></span>

<span data-ttu-id="39949-103">Define un atributo de interfaz personalizada que especifica el nombre de espacio de nombres administrado para una biblioteca COM (modelo de objetos componentes).</span><span class="sxs-lookup"><span data-stu-id="39949-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39949-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39949-104">Syntax</span></span>  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="39949-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39949-105">Parameters</span></span>  

 `value`  
 <span data-ttu-id="39949-106">Nombre del espacio de nombres administrado de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="39949-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="39949-107">Definición</span><span class="sxs-lookup"><span data-stu-id="39949-107">Definition</span></span>  

 <span data-ttu-id="39949-108">`GUID_ManagedName` se define en Cor. h de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="39949-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="39949-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39949-109">Remarks</span></span>  

 <span data-ttu-id="39949-110">Un atributo de interfaz personalizada define los metadatos de un objeto en la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="39949-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="39949-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> para recuperar el nombre administrado del atributo.</span><span class="sxs-lookup"><span data-stu-id="39949-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="39949-112">Para obtener más información, vea [atributos de interfaz](/cpp/windows/attributes/interface-attributes) en la documentación de referencia de Visual C++.</span><span class="sxs-lookup"><span data-stu-id="39949-112">For more information, see [Interface Attributes](/cpp/windows/attributes/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39949-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39949-113">Example</span></span>  

 <span data-ttu-id="39949-114">En el ejemplo siguiente se muestra una definición de biblioteca mediante el `GUID_ManagedName` atributo.</span><span class="sxs-lookup"><span data-stu-id="39949-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="39949-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39949-115">Requirements</span></span>  

 <span data-ttu-id="39949-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39949-116">**Header:** Cor.h</span></span>
