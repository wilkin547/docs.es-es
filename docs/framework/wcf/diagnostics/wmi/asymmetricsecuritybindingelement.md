---
description: 'Más información acerca de: AsymmetricSecurityBindingElement'
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 25d0ac205491e9ce27c59d3a0670d1e4a3150e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757948"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="aadb7-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="aadb7-103">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="aadb7-104">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="aadb7-104">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aadb7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aadb7-105">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="aadb7-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="aadb7-106">Methods</span></span>  

 <span data-ttu-id="aadb7-107">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="aadb7-107">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="aadb7-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="aadb7-108">Properties</span></span>  

 <span data-ttu-id="aadb7-109">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="aadb7-109">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="aadb7-110">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="aadb7-110">MessageProtectionOrder</span></span>  

 <span data-ttu-id="aadb7-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="aadb7-111">Data type: string</span></span>  
  
 <span data-ttu-id="aadb7-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="aadb7-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aadb7-113">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="aadb7-113">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="aadb7-114">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="aadb7-114">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="aadb7-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="aadb7-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="aadb7-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="aadb7-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aadb7-117">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="aadb7-117">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aadb7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aadb7-118">Requirements</span></span>  
  
|<span data-ttu-id="aadb7-119">MOF</span><span class="sxs-lookup"><span data-stu-id="aadb7-119">MOF</span></span>|<span data-ttu-id="aadb7-120">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="aadb7-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="aadb7-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="aadb7-121">Namespace</span></span>|<span data-ttu-id="aadb7-122">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aadb7-122">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aadb7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="aadb7-123">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
