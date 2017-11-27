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
ms.openlocfilehash: cf0facaa1107fcc6dcd93cbf0252024dc6f73b0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="238bf-102">GUID_ManagedName (Atributo)</span><span class="sxs-lookup"><span data-stu-id="238bf-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="238bf-103">Define un atributo de interfaz personalizado que especifica el nombre de espacio de nombres administrado para una biblioteca de (componentes COM) del modelo de objetos de componente.</span><span class="sxs-lookup"><span data-stu-id="238bf-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="238bf-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="238bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="238bf-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="238bf-106">El nombre de espacio de nombres administrado para la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="238bf-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="238bf-107">Definición</span><span class="sxs-lookup"><span data-stu-id="238bf-107">Definition</span></span>  
 <span data-ttu-id="238bf-108">`GUID_ManagedName`se define en Cor.h como sigue:</span><span class="sxs-lookup"><span data-stu-id="238bf-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="238bf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="238bf-109">Remarks</span></span>  
 <span data-ttu-id="238bf-110">Un atributo de interfaz personalizado define los metadatos de un objeto en la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="238bf-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="238bf-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> para recuperar el nombre administrado del atributo.</span><span class="sxs-lookup"><span data-stu-id="238bf-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="238bf-112">Para obtener más información, consulte [atributos de la interfaz](/cpp/windows/interface-attributes) documentación de referencia de Visual C++.</span><span class="sxs-lookup"><span data-stu-id="238bf-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="238bf-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="238bf-113">Example</span></span>  
 <span data-ttu-id="238bf-114">En el ejemplo siguiente se muestra una definición de biblioteca mediante el `GUID_ManagedName` atributo.</span><span class="sxs-lookup"><span data-stu-id="238bf-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="238bf-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="238bf-115">Requirements</span></span>  
 <span data-ttu-id="238bf-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="238bf-116">**Header:** Cor.h</span></span>
