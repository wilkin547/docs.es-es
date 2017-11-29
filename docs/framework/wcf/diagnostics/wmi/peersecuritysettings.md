---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 02cd483f2f7ec5e599b286b672d051a0e8d57940
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="802f8-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="802f8-102">PeerSecuritySettings</span></span>
<span data-ttu-id="802f8-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="802f8-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="802f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="802f8-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="802f8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="802f8-105">Methods</span></span>  
 <span data-ttu-id="802f8-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="802f8-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="802f8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="802f8-107">Properties</span></span>  
 <span data-ttu-id="802f8-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="802f8-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="802f8-109">Modo</span><span class="sxs-lookup"><span data-stu-id="802f8-109">Mode</span></span>  
 <span data-ttu-id="802f8-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="802f8-110">Data type: string</span></span>  
  
 <span data-ttu-id="802f8-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="802f8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="802f8-112">Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="802f8-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="802f8-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="802f8-113">Transport</span></span>  
 <span data-ttu-id="802f8-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="802f8-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="802f8-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="802f8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="802f8-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="802f8-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="802f8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="802f8-117">Requirements</span></span>  
  
|<span data-ttu-id="802f8-118">MOF</span><span class="sxs-lookup"><span data-stu-id="802f8-118">MOF</span></span>|<span data-ttu-id="802f8-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="802f8-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="802f8-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="802f8-120">Namespace</span></span>|<span data-ttu-id="802f8-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="802f8-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="802f8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="802f8-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
