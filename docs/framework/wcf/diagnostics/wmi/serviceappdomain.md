---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273261"
---
# <a name="serviceappdomain"></a><span data-ttu-id="79607-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="79607-102">ServiceAppDomain</span></span>

<span data-ttu-id="79607-103">Asigna un servicio a un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="79607-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79607-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79607-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="79607-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="79607-105">Methods</span></span>  

 <span data-ttu-id="79607-106">La clase ServiceAppDomain no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="79607-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="79607-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="79607-107">Properties</span></span>  

 <span data-ttu-id="79607-108">La clase ServiceAppDomain posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="79607-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="79607-109">ref</span><span class="sxs-lookup"><span data-stu-id="79607-109">ref</span></span>  

 <span data-ttu-id="79607-110">Tipo de datos: servicio</span><span class="sxs-lookup"><span data-stu-id="79607-110">Data type: Service</span></span>  
<span data-ttu-id="79607-111">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="79607-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="79607-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="79607-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79607-113">Servicio de este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="79607-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="79607-114">ref</span><span class="sxs-lookup"><span data-stu-id="79607-114">ref</span></span>  

 <span data-ttu-id="79607-115">Tipo de datos: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="79607-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="79607-116">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="79607-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="79607-117">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="79607-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79607-118">Contiene propiedades del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="79607-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79607-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79607-119">Requirements</span></span>  
  
|<span data-ttu-id="79607-120">MOF</span><span class="sxs-lookup"><span data-stu-id="79607-120">MOF</span></span>|<span data-ttu-id="79607-121">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="79607-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="79607-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="79607-122">Namespace</span></span>|<span data-ttu-id="79607-123">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="79607-123">Defined in root\ServiceModel</span></span>|
