---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269007"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="d13c6-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d13c6-102">PeerSecuritySettings</span></span>

<span data-ttu-id="d13c6-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d13c6-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d13c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d13c6-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d13c6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d13c6-105">Methods</span></span>  

 <span data-ttu-id="d13c6-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d13c6-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d13c6-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d13c6-107">Properties</span></span>  

 <span data-ttu-id="d13c6-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="d13c6-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="d13c6-109">Mode</span><span class="sxs-lookup"><span data-stu-id="d13c6-109">Mode</span></span>  

 <span data-ttu-id="d13c6-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d13c6-110">Data type: string</span></span>  
  
 <span data-ttu-id="d13c6-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d13c6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d13c6-112">Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="d13c6-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="d13c6-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="d13c6-113">Transport</span></span>  

 <span data-ttu-id="d13c6-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d13c6-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="d13c6-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d13c6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d13c6-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="d13c6-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d13c6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d13c6-117">Requirements</span></span>  
  
|<span data-ttu-id="d13c6-118">MOF</span><span class="sxs-lookup"><span data-stu-id="d13c6-118">MOF</span></span>|<span data-ttu-id="d13c6-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d13c6-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d13c6-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d13c6-120">Namespace</span></span>|<span data-ttu-id="d13c6-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d13c6-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d13c6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d13c6-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
