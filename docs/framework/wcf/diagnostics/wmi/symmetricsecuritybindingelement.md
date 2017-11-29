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
ms.openlocfilehash: ab341f55947bfcfbc776143e3bbc33e125da89c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="e32a7-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e32a7-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="e32a7-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e32a7-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e32a7-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e32a7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e32a7-105">Methods</span></span>  
 <span data-ttu-id="e32a7-106">La clase SymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e32a7-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e32a7-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e32a7-107">Properties</span></span>  
 <span data-ttu-id="e32a7-108">La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e32a7-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="e32a7-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="e32a7-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="e32a7-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e32a7-110">Data type: string</span></span>  
  
 <span data-ttu-id="e32a7-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e32a7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e32a7-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="e32a7-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="e32a7-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="e32a7-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="e32a7-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e32a7-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="e32a7-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e32a7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e32a7-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="e32a7-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32a7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e32a7-117">Requirements</span></span>  
  
|<span data-ttu-id="e32a7-118">MOF</span><span class="sxs-lookup"><span data-stu-id="e32a7-118">MOF</span></span>|<span data-ttu-id="e32a7-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e32a7-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e32a7-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e32a7-120">Namespace</span></span>|<span data-ttu-id="e32a7-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e32a7-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e32a7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e32a7-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
