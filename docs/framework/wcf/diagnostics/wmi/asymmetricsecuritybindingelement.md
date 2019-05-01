---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964208"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="d4cc4-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4cc4-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="d4cc4-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4cc4-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4cc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4cc4-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d4cc4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4cc4-105">Methods</span></span>  
 <span data-ttu-id="d4cc4-106">La clase AsymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d4cc4-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d4cc4-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d4cc4-107">Properties</span></span>  
 <span data-ttu-id="d4cc4-108">La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="d4cc4-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="d4cc4-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="d4cc4-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="d4cc4-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d4cc4-110">Data type: string</span></span>  
  
 <span data-ttu-id="d4cc4-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d4cc4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4cc4-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="d4cc4-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="d4cc4-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="d4cc4-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="d4cc4-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d4cc4-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d4cc4-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="d4cc4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4cc4-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="d4cc4-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4cc4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4cc4-117">Requirements</span></span>  
  
|<span data-ttu-id="d4cc4-118">MOF</span><span class="sxs-lookup"><span data-stu-id="d4cc4-118">MOF</span></span>|<span data-ttu-id="d4cc4-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d4cc4-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d4cc4-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d4cc4-120">Namespace</span></span>|<span data-ttu-id="d4cc4-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d4cc4-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4cc4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4cc4-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
