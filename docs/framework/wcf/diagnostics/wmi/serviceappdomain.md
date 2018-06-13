---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485673"
---
# <a name="serviceappdomain"></a><span data-ttu-id="3abbd-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="3abbd-102">ServiceAppDomain</span></span>
<span data-ttu-id="3abbd-103">Asigna un servicio a un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3abbd-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abbd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3abbd-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3abbd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3abbd-105">Methods</span></span>  
 <span data-ttu-id="3abbd-106">La clase ServiceAppDomain no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="3abbd-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3abbd-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3abbd-107">Properties</span></span>  
 <span data-ttu-id="3abbd-108">La clase ServiceAppDomain posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3abbd-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="3abbd-109">ref</span><span class="sxs-lookup"><span data-stu-id="3abbd-109">ref</span></span>  
 <span data-ttu-id="3abbd-110">Tipo de datos: servicio</span><span class="sxs-lookup"><span data-stu-id="3abbd-110">Data type: Service</span></span>  
<span data-ttu-id="3abbd-111">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="3abbd-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="3abbd-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3abbd-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3abbd-113">Servicio de este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3abbd-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="3abbd-114">ref</span><span class="sxs-lookup"><span data-stu-id="3abbd-114">ref</span></span>  
 <span data-ttu-id="3abbd-115">Tipo de datos: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="3abbd-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="3abbd-116">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="3abbd-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="3abbd-117">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3abbd-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3abbd-118">Contiene propiedades del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3abbd-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3abbd-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3abbd-119">Requirements</span></span>  
  
|<span data-ttu-id="3abbd-120">MOF</span><span class="sxs-lookup"><span data-stu-id="3abbd-120">MOF</span></span>|<span data-ttu-id="3abbd-121">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3abbd-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3abbd-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="3abbd-122">Namespace</span></span>|<span data-ttu-id="3abbd-123">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3abbd-123">Defined in root\ServiceModel</span></span>|
