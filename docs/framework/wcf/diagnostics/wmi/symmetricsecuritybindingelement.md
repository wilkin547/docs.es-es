---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: c618b5b41790b04a84b4c50fe47baa2c0cb05ab2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274106"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="fb068-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fb068-102">SymmetricSecurityBindingElement</span></span>

<span data-ttu-id="fb068-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fb068-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb068-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb068-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb068-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb068-105">Methods</span></span>  

 <span data-ttu-id="fb068-106">La clase SymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fb068-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb068-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fb068-107">Properties</span></span>  

 <span data-ttu-id="fb068-108">La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb068-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="fb068-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="fb068-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="fb068-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fb068-110">Data type: string</span></span>  
  
 <span data-ttu-id="fb068-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fb068-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb068-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="fb068-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="fb068-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="fb068-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="fb068-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fb068-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb068-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fb068-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb068-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="fb068-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb068-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb068-117">Requirements</span></span>  
  
|<span data-ttu-id="fb068-118">MOF</span><span class="sxs-lookup"><span data-stu-id="fb068-118">MOF</span></span>|<span data-ttu-id="fb068-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb068-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb068-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fb068-120">Namespace</span></span>|<span data-ttu-id="fb068-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fb068-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb068-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb068-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
