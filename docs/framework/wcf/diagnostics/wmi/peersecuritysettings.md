---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976903"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="ea9ab-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ea9ab-102">PeerSecuritySettings</span></span>
<span data-ttu-id="ea9ab-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ea9ab-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea9ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea9ab-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ea9ab-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ea9ab-105">Methods</span></span>  
 <span data-ttu-id="ea9ab-106">La clase PeerSecuritySettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ea9ab-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ea9ab-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ea9ab-107">Properties</span></span>  
 <span data-ttu-id="ea9ab-108">La clase PeerSecuritySettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="ea9ab-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="ea9ab-109">Modo</span><span class="sxs-lookup"><span data-stu-id="ea9ab-109">Mode</span></span>  
 <span data-ttu-id="ea9ab-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ea9ab-110">Data type: string</span></span>  
  
 <span data-ttu-id="ea9ab-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ea9ab-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea9ab-112">Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.</span><span class="sxs-lookup"><span data-stu-id="ea9ab-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="ea9ab-113">Transporte</span><span class="sxs-lookup"><span data-stu-id="ea9ab-113">Transport</span></span>  
 <span data-ttu-id="ea9ab-114">Tipo de datos: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ea9ab-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="ea9ab-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ea9ab-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ea9ab-116">Valores de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="ea9ab-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea9ab-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea9ab-117">Requirements</span></span>  
  
|<span data-ttu-id="ea9ab-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ea9ab-118">MOF</span></span>|<span data-ttu-id="ea9ab-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ea9ab-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ea9ab-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ea9ab-120">Namespace</span></span>|<span data-ttu-id="ea9ab-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ea9ab-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea9ab-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea9ab-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
