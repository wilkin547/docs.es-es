---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397363"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="f53e5-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f53e5-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="f53e5-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f53e5-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f53e5-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f53e5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f53e5-105">Methods</span></span>  
 <span data-ttu-id="f53e5-106">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f53e5-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f53e5-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f53e5-107">Properties</span></span>  
 <span data-ttu-id="f53e5-108">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f53e5-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="f53e5-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="f53e5-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="f53e5-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f53e5-110">Data type: string</span></span>  
  
 <span data-ttu-id="f53e5-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f53e5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f53e5-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="f53e5-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="f53e5-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="f53e5-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="f53e5-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f53e5-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f53e5-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f53e5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f53e5-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="f53e5-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f53e5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f53e5-117">Requirements</span></span>  
  
|<span data-ttu-id="f53e5-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f53e5-118">MOF</span></span>|<span data-ttu-id="f53e5-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f53e5-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f53e5-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f53e5-120">Namespace</span></span>|<span data-ttu-id="f53e5-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f53e5-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f53e5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53e5-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
