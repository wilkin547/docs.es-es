---
description: 'Más información acerca de: PeerSecuritySettings'
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: a8b5b8c88e71cb46110fa35186599c0f9c366d17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803014"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="460cd-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="460cd-103">PeerSecuritySettings</span></span>

<span data-ttu-id="460cd-104">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="460cd-104">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="460cd-105">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="460cd-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="460cd-106">Methods</span></span>  

 <span data-ttu-id="460cd-107">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="460cd-107">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="460cd-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="460cd-108">Properties</span></span>  

 <span data-ttu-id="460cd-109">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="460cd-109">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="460cd-110">Modo</span><span class="sxs-lookup"><span data-stu-id="460cd-110">Mode</span></span>  

 <span data-ttu-id="460cd-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="460cd-111">Data type: string</span></span>  
  
 <span data-ttu-id="460cd-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="460cd-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="460cd-113">Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="460cd-113">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="460cd-114">Transporte</span><span class="sxs-lookup"><span data-stu-id="460cd-114">Transport</span></span>  

 <span data-ttu-id="460cd-115">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="460cd-115">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="460cd-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="460cd-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="460cd-117">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="460cd-117">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="460cd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="460cd-118">Requirements</span></span>  
  
|<span data-ttu-id="460cd-119">MOF</span><span class="sxs-lookup"><span data-stu-id="460cd-119">MOF</span></span>|<span data-ttu-id="460cd-120">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="460cd-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="460cd-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="460cd-121">Namespace</span></span>|<span data-ttu-id="460cd-122">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="460cd-122">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="460cd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="460cd-123">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
