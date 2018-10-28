---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 92aca4c790607de91314aacf6414d0dfacea9a9f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193167"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="03ddd-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="03ddd-102">PeerSecuritySettings</span></span>
<span data-ttu-id="03ddd-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="03ddd-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ddd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03ddd-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="03ddd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="03ddd-105">Methods</span></span>  
 <span data-ttu-id="03ddd-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="03ddd-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="03ddd-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="03ddd-107">Properties</span></span>  
 <span data-ttu-id="03ddd-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="03ddd-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="03ddd-109">Modo</span><span class="sxs-lookup"><span data-stu-id="03ddd-109">Mode</span></span>  
 <span data-ttu-id="03ddd-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="03ddd-110">Data type: string</span></span>  
  
 <span data-ttu-id="03ddd-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03ddd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03ddd-112">Si un punto de conexión configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="03ddd-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="03ddd-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="03ddd-113">Transport</span></span>  
 <span data-ttu-id="03ddd-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="03ddd-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="03ddd-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="03ddd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="03ddd-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="03ddd-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03ddd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03ddd-117">Requirements</span></span>  
  
|<span data-ttu-id="03ddd-118">MOF</span><span class="sxs-lookup"><span data-stu-id="03ddd-118">MOF</span></span>|<span data-ttu-id="03ddd-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="03ddd-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="03ddd-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="03ddd-120">Namespace</span></span>|<span data-ttu-id="03ddd-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="03ddd-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03ddd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="03ddd-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
