---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075062"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="ac2b0-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ac2b0-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="ac2b0-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ac2b0-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac2b0-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ac2b0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ac2b0-105">Methods</span></span>  
 <span data-ttu-id="ac2b0-106">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ac2b0-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ac2b0-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ac2b0-107">Properties</span></span>  
 <span data-ttu-id="ac2b0-108">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac2b0-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="ac2b0-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="ac2b0-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="ac2b0-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ac2b0-110">Data type: string</span></span>  
  
 <span data-ttu-id="ac2b0-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ac2b0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ac2b0-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="ac2b0-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="ac2b0-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="ac2b0-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="ac2b0-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="ac2b0-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ac2b0-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ac2b0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ac2b0-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="ac2b0-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2b0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac2b0-117">Requirements</span></span>  
  
|<span data-ttu-id="ac2b0-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ac2b0-118">MOF</span></span>|<span data-ttu-id="ac2b0-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ac2b0-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ac2b0-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ac2b0-120">Namespace</span></span>|<span data-ttu-id="ac2b0-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ac2b0-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac2b0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac2b0-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
