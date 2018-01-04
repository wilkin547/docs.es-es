---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7960ae9972490f2363b0f6f9942e947677c7d299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="c14bd-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c14bd-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="c14bd-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c14bd-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c14bd-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c14bd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c14bd-105">Methods</span></span>  
 <span data-ttu-id="c14bd-106">La clase SymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c14bd-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c14bd-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c14bd-107">Properties</span></span>  
 <span data-ttu-id="c14bd-108">La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="c14bd-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="c14bd-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="c14bd-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="c14bd-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c14bd-110">Data type: string</span></span>  
  
 <span data-ttu-id="c14bd-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c14bd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c14bd-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="c14bd-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="c14bd-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="c14bd-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="c14bd-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="c14bd-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="c14bd-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c14bd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c14bd-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="c14bd-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c14bd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c14bd-117">Requirements</span></span>  
  
|<span data-ttu-id="c14bd-118">MOF</span><span class="sxs-lookup"><span data-stu-id="c14bd-118">MOF</span></span>|<span data-ttu-id="c14bd-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c14bd-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c14bd-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c14bd-120">Namespace</span></span>|<span data-ttu-id="c14bd-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c14bd-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c14bd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c14bd-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
