---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 82e5365a440d103727f354e682d0ebecb5f46a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="f9de2-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f9de2-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="f9de2-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f9de2-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9de2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9de2-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f9de2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f9de2-105">Methods</span></span>  
 <span data-ttu-id="f9de2-106">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f9de2-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f9de2-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f9de2-107">Properties</span></span>  
 <span data-ttu-id="f9de2-108">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9de2-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="f9de2-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="f9de2-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="f9de2-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f9de2-110">Data type: string</span></span>  
  
 <span data-ttu-id="f9de2-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f9de2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9de2-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="f9de2-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="f9de2-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="f9de2-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="f9de2-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f9de2-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f9de2-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f9de2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9de2-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="f9de2-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9de2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9de2-117">Requirements</span></span>  
  
|<span data-ttu-id="f9de2-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f9de2-118">MOF</span></span>|<span data-ttu-id="f9de2-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f9de2-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f9de2-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f9de2-120">Namespace</span></span>|<span data-ttu-id="f9de2-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f9de2-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9de2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9de2-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
