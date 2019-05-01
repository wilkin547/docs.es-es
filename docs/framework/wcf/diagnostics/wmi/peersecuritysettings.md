---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963012"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="368e0-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="368e0-102">PeerSecuritySettings</span></span>
<span data-ttu-id="368e0-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="368e0-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="368e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="368e0-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="368e0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="368e0-105">Methods</span></span>  
 <span data-ttu-id="368e0-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="368e0-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="368e0-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="368e0-107">Properties</span></span>  
 <span data-ttu-id="368e0-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="368e0-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="368e0-109">Modo</span><span class="sxs-lookup"><span data-stu-id="368e0-109">Mode</span></span>  
 <span data-ttu-id="368e0-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="368e0-110">Data type: string</span></span>  
  
 <span data-ttu-id="368e0-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="368e0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="368e0-112">Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="368e0-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="368e0-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="368e0-113">Transport</span></span>  
 <span data-ttu-id="368e0-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="368e0-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="368e0-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="368e0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="368e0-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="368e0-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="368e0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="368e0-117">Requirements</span></span>  
  
|<span data-ttu-id="368e0-118">MOF</span><span class="sxs-lookup"><span data-stu-id="368e0-118">MOF</span></span>|<span data-ttu-id="368e0-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="368e0-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="368e0-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="368e0-120">Namespace</span></span>|<span data-ttu-id="368e0-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="368e0-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="368e0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="368e0-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
