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
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="f1d03-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f1d03-102">PeerSecuritySettings</span></span>
<span data-ttu-id="f1d03-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f1d03-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d03-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1d03-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f1d03-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f1d03-105">Methods</span></span>  
 <span data-ttu-id="f1d03-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f1d03-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f1d03-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f1d03-107">Properties</span></span>  
 <span data-ttu-id="f1d03-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="f1d03-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="f1d03-109">Modo</span><span class="sxs-lookup"><span data-stu-id="f1d03-109">Mode</span></span>  
 <span data-ttu-id="f1d03-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f1d03-110">Data type: string</span></span>  
  
 <span data-ttu-id="f1d03-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f1d03-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f1d03-112">Si un punto de conexión configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1d03-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="f1d03-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="f1d03-113">Transport</span></span>  
 <span data-ttu-id="f1d03-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="f1d03-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="f1d03-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f1d03-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f1d03-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1d03-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d03-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1d03-117">Requirements</span></span>  
  
|<span data-ttu-id="f1d03-118">MOF</span><span class="sxs-lookup"><span data-stu-id="f1d03-118">MOF</span></span>|<span data-ttu-id="f1d03-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f1d03-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f1d03-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f1d03-120">Namespace</span></span>|<span data-ttu-id="f1d03-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f1d03-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1d03-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1d03-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
