---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: e633ae19cd17930fb140a93ffd0910c7ed8efea4
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374438"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="6010e-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6010e-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="6010e-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6010e-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6010e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6010e-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6010e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6010e-105">Methods</span></span>  
 <span data-ttu-id="6010e-106">La clase SymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6010e-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6010e-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6010e-107">Properties</span></span>  
 <span data-ttu-id="6010e-108">La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6010e-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="6010e-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="6010e-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="6010e-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6010e-110">Data type: string</span></span>  
  
 <span data-ttu-id="6010e-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6010e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6010e-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="6010e-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="6010e-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="6010e-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="6010e-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6010e-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="6010e-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6010e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6010e-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="6010e-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6010e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6010e-117">Requirements</span></span>  
  
|<span data-ttu-id="6010e-118">MOF</span><span class="sxs-lookup"><span data-stu-id="6010e-118">MOF</span></span>|<span data-ttu-id="6010e-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6010e-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6010e-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6010e-120">Namespace</span></span>|<span data-ttu-id="6010e-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6010e-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6010e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6010e-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
