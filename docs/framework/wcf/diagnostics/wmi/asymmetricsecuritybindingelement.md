---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255733"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="52ab0-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="52ab0-102">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="52ab0-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="52ab0-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ab0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52ab0-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="52ab0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="52ab0-105">Methods</span></span>  

 <span data-ttu-id="52ab0-106">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="52ab0-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="52ab0-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="52ab0-107">Properties</span></span>  

 <span data-ttu-id="52ab0-108">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="52ab0-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="52ab0-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="52ab0-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="52ab0-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="52ab0-110">Data type: string</span></span>  
  
 <span data-ttu-id="52ab0-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="52ab0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52ab0-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="52ab0-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="52ab0-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="52ab0-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="52ab0-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="52ab0-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="52ab0-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="52ab0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52ab0-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="52ab0-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ab0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52ab0-117">Requirements</span></span>  
  
|<span data-ttu-id="52ab0-118">MOF</span><span class="sxs-lookup"><span data-stu-id="52ab0-118">MOF</span></span>|<span data-ttu-id="52ab0-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="52ab0-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="52ab0-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="52ab0-120">Namespace</span></span>|<span data-ttu-id="52ab0-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="52ab0-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52ab0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ab0-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
