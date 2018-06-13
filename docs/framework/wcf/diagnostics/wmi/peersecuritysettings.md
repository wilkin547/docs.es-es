---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 58b372f26fee7dc180d75731fd4855db569c87c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484526"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="363c4-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="363c4-102">PeerSecuritySettings</span></span>
<span data-ttu-id="363c4-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="363c4-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="363c4-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="363c4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="363c4-105">Methods</span></span>  
 <span data-ttu-id="363c4-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="363c4-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="363c4-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="363c4-107">Properties</span></span>  
 <span data-ttu-id="363c4-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="363c4-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="363c4-109">Modo</span><span class="sxs-lookup"><span data-stu-id="363c4-109">Mode</span></span>  
 <span data-ttu-id="363c4-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="363c4-110">Data type: string</span></span>  
  
 <span data-ttu-id="363c4-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="363c4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="363c4-112">Si un punto de conexión configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="363c4-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="363c4-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="363c4-113">Transport</span></span>  
 <span data-ttu-id="363c4-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="363c4-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="363c4-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="363c4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="363c4-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="363c4-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="363c4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="363c4-117">Requirements</span></span>  
  
|<span data-ttu-id="363c4-118">MOF</span><span class="sxs-lookup"><span data-stu-id="363c4-118">MOF</span></span>|<span data-ttu-id="363c4-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="363c4-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="363c4-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="363c4-120">Namespace</span></span>|<span data-ttu-id="363c4-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="363c4-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="363c4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="363c4-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
