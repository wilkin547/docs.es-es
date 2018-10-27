---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: 26bd0c95f930bf7859ae6409d797afbb596844fa
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180672"
---
# <a name="servicecredentials"></a><span data-ttu-id="4b818-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4b818-102">ServiceCredentials</span></span>
<span data-ttu-id="4b818-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4b818-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b818-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b818-104">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4b818-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4b818-105">Methods</span></span>  
 <span data-ttu-id="4b818-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="4b818-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4b818-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4b818-107">Properties</span></span>  
 <span data-ttu-id="4b818-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="4b818-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="4b818-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4b818-109">ClientCertificate</span></span>  
 <span data-ttu-id="4b818-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-110">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="4b818-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="4b818-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b818-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="4b818-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-114">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="4b818-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="4b818-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="4b818-117">Peer</span></span>  
 <span data-ttu-id="4b818-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-118">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los extremos de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="4b818-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="4b818-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b818-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="4b818-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-122">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="4b818-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="4b818-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="4b818-125">ServiceCertificate</span></span>  
 <span data-ttu-id="4b818-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-126">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="4b818-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="4b818-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b818-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="4b818-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-130">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="4b818-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="4b818-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="4b818-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="4b818-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4b818-134">Data type: string</span></span>  
  
 <span data-ttu-id="4b818-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4b818-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b818-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="4b818-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b818-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b818-137">Requirements</span></span>  
  
|<span data-ttu-id="4b818-138">MOF</span><span class="sxs-lookup"><span data-stu-id="4b818-138">MOF</span></span>|<span data-ttu-id="4b818-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4b818-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4b818-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4b818-140">Namespace</span></span>|<span data-ttu-id="4b818-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4b818-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b818-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b818-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
