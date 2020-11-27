---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262312"
---
# <a name="servicecredentials"></a><span data-ttu-id="bdb3c-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="bdb3c-102">ServiceCredentials</span></span>

<span data-ttu-id="bdb3c-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="bdb3c-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdb3c-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bdb3c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bdb3c-105">Methods</span></span>  

 <span data-ttu-id="bdb3c-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bdb3c-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bdb3c-107">Properties</span></span>  

 <span data-ttu-id="bdb3c-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="bdb3c-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="bdb3c-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="bdb3c-109">ClientCertificate</span></span>  

 <span data-ttu-id="bdb3c-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-110">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="bdb3c-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="bdb3c-113">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="bdb3c-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-114">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="bdb3c-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="bdb3c-117">Peer</span></span>  

 <span data-ttu-id="bdb3c-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-118">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los puntos de conexión de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="bdb3c-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="bdb3c-121">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="bdb3c-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-122">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="bdb3c-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="bdb3c-125">ServiceCertificate</span></span>  

 <span data-ttu-id="bdb3c-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-126">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="bdb3c-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="bdb3c-129">UserNameAuthentication</span></span>  

 <span data-ttu-id="bdb3c-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-130">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="bdb3c-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="bdb3c-133">WindowsAuthentication</span></span>  

 <span data-ttu-id="bdb3c-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="bdb3c-134">Data type: string</span></span>  
  
 <span data-ttu-id="bdb3c-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bdb3c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bdb3c-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb3c-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdb3c-137">Requirements</span></span>  
  
|<span data-ttu-id="bdb3c-138">MOF</span><span class="sxs-lookup"><span data-stu-id="bdb3c-138">MOF</span></span>|<span data-ttu-id="bdb3c-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bdb3c-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bdb3c-140">Namespace</span></span>|<span data-ttu-id="bdb3c-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bdb3c-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdb3c-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdb3c-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
