---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196052"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="08495-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="08495-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="08495-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="08495-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08495-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="08495-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="08495-105">Methods</span></span>  
 <span data-ttu-id="08495-106">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="08495-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="08495-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="08495-107">Properties</span></span>  
 <span data-ttu-id="08495-108">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="08495-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="08495-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="08495-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="08495-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08495-110">Data type: string</span></span>  
  
 <span data-ttu-id="08495-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="08495-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08495-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="08495-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="08495-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="08495-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="08495-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08495-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="08495-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="08495-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08495-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="08495-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08495-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08495-117">Requirements</span></span>  
  
|<span data-ttu-id="08495-118">MOF</span><span class="sxs-lookup"><span data-stu-id="08495-118">MOF</span></span>|<span data-ttu-id="08495-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="08495-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="08495-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="08495-120">Namespace</span></span>|<span data-ttu-id="08495-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08495-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08495-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="08495-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
