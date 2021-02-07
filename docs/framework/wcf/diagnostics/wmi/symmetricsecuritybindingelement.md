---
description: 'Más información acerca de: SymmetricSecurityBindingElement'
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c158f0bedec91a74b305f359889dd307cff48079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715306"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="87c0c-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="87c0c-103">SymmetricSecurityBindingElement</span></span>

<span data-ttu-id="87c0c-104">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="87c0c-104">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87c0c-105">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87c0c-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="87c0c-106">Methods</span></span>  

 <span data-ttu-id="87c0c-107">La clase SymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="87c0c-107">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87c0c-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="87c0c-108">Properties</span></span>  

 <span data-ttu-id="87c0c-109">La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="87c0c-109">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="87c0c-110">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="87c0c-110">MessageProtectionOrder</span></span>  

 <span data-ttu-id="87c0c-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="87c0c-111">Data type: string</span></span>  
  
 <span data-ttu-id="87c0c-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="87c0c-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87c0c-113">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="87c0c-113">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="87c0c-114">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="87c0c-114">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="87c0c-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="87c0c-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="87c0c-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="87c0c-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87c0c-117">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="87c0c-117">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c0c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87c0c-118">Requirements</span></span>  
  
|<span data-ttu-id="87c0c-119">MOF</span><span class="sxs-lookup"><span data-stu-id="87c0c-119">MOF</span></span>|<span data-ttu-id="87c0c-120">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="87c0c-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87c0c-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="87c0c-121">Namespace</span></span>|<span data-ttu-id="87c0c-122">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87c0c-122">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87c0c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="87c0c-123">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
